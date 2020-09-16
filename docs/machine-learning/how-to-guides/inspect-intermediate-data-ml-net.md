---
title: Inspekcja danych pośrednich podczas przetwarzania ML.NET
description: Dowiedz się, jak przeprowadzać inspekcję danych pośrednich podczas ML.NETu załadowania, przetwarzania i modelowania potoku uczenia maszynowego w ML.NET.
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 4f168653297594a604e6f381947f31cba5376178
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679628"
---
# <a name="inspect-intermediate-data-during-processing"></a>Inspekcja danych pośrednich podczas przetwarzania

Dowiedz się, jak przeprowadzać inspekcję danych pośrednich podczas procesu ładowania, przetwarzania i tworzenia modeli w ML.NET. Dane pośrednie są danymi wyjściowymi każdego etapu w potoku uczenia maszynowego.

Dane pośrednie, takie jak reprezentowane poniżej, które są ładowane do programu, [`IDataView`](xref:Microsoft.ML.IDataView) można sprawdzić na różne sposoby w ml.NET.

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

## <a name="convert-idataview-to-ienumerable"></a>Konwertuj IDataView na interfejs IEnumerable

Jednym z najszybszych sposobów na sprawdzenie programu [`IDataView`](xref:Microsoft.ML.IDataView) jest przekształcenie go w [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) . Aby przekonwertować [`IDataView`](xref:Microsoft.ML.IDataView) metodę, aby [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) użyć [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) metody.

Aby zoptymalizować wydajność, ustaw `reuseRowObject` wartość `true` . Wykonanie tej czynności spowoduje opóźnieniem wypełnienie tego samego obiektu danymi bieżącego wiersza, ponieważ jest ono oceniane jako przeciwieństwem do tworzenia nowego obiektu dla każdego wiersza w zestawie danych.

```csharp
// Create an IEnumerable of HousingData objects from IDataView
IEnumerable<HousingData> housingDataEnumerable =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: true);

// Iterate over each row
foreach (HousingData row in housingDataEnumerable)
{
    // Do something (print out Size property) with current Housing Data object being evaluated
    Console.WriteLine(row.Size);
}
```

## <a name="accessing-specific-indices-with-ienumerable"></a>Uzyskiwanie dostępu do określonych indeksów przy użyciu interfejsu IEnumerable

Jeśli potrzebujesz tylko dostępu do części danych lub określonych indeksów, użyj [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) i ustaw `reuseRowObject` wartość parametru na tak, aby `false` nowy obiekt został utworzony dla każdego z żądanych wierszy w zestawie danych. Następnie przekonwertuj [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) na tablicę lub listę.

> [!WARNING]
> Konwersja wyniku [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) do tablicy lub listy spowoduje załadowanie wszystkich żądanych [`IDataView`](xref:Microsoft.ML.IDataView) wierszy do pamięci, co może wpłynąć na wydajność.

Po utworzeniu kolekcji można wykonywać operacje na danych. Poniższy fragment kodu pobiera pierwsze trzy wiersze w zestawie danych i oblicza średnią bieżącą cenę.

```csharp
// Create an Array of HousingData objects from IDataView
HousingData[] housingDataArray =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: false)
        .Take(3)
        .ToArray();

// Calculate Average CurrentPrice of First Three Elements
HousingData firstRow = housingDataArray[0];
HousingData secondRow = housingDataArray[1];
HousingData thirdRow = housingDataArray[2];
float averageCurrentPrice = (firstRow.CurrentPrice + secondRow.CurrentPrice + thirdRow.CurrentPrice) / 3;
```

## <a name="inspect-values-in-a-single-column"></a>Inspekcja wartości w pojedynczej kolumnie

W dowolnym momencie procesu tworzenia modelu wartości w jednej kolumnie są [`IDataView`](xref:Microsoft.ML.IDataView) dostępne przy użyciu [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn%2A) metody. [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn%2A)Metoda zwraca wszystkie wartości z pojedynczej kolumny jako [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) .

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a>Inspekcja wartości IDataView po jednym wierszu

[`IDataView`](xref:Microsoft.ML.IDataView) opóźnieniem. Aby wykonać iterację wierszy [`IDataView`](xref:Microsoft.ML.IDataView) bez konwersji na [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) tak jak pokazano w poprzednich sekcjach tego dokumentu, Utwórz [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) za pomocą [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor%2A) metody i przekazując w [DataViewSchema](xref:Microsoft.ML.DataViewSchema) [`IDataView`](xref:Microsoft.ML.IDataView) jako parametr. Następnie, aby wykonać iterację wierszy, użyj [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext%2A) metody Cursor wraz z [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegatami, aby wyodrębnić odpowiednie wartości z poszczególnych kolumn.

> [!IMPORTANT]
> W celu zapewnienia wydajności wektory w ML.NET używają [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) zamiast natywnych typów kolekcji (czyli `Vector` , `float[]` ).

```csharp
// Get DataViewSchema of IDataView
DataViewSchema columns = data.Schema;

// Create DataViewCursor
using (DataViewRowCursor cursor = data.GetRowCursor(columns))
{
    // Define variables where extracted values will be stored to
    float size = default;
    VBuffer<float> historicalPrices = default;
    float currentPrice = default;

    // Define delegates for extracting values from columns
    ValueGetter<float> sizeDelegate = cursor.GetGetter<float>(columns[0]);
    ValueGetter<VBuffer<float>> historicalPriceDelegate = cursor.GetGetter<VBuffer<float>>(columns[1]);
    ValueGetter<float> currentPriceDelegate = cursor.GetGetter<float>(columns[2]);

    // Iterate over each row
    while (cursor.MoveNext())
    {
        //Get values from respective columns
        sizeDelegate.Invoke(ref size);
        historicalPriceDelegate.Invoke(ref historicalPrices);
        currentPriceDelegate.Invoke(ref currentPrice);
    }
}
```

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a>Podgląd wyniku wstępnego przetwarzania lub szkoleń dotyczących podzestawu danych

> [!WARNING]
> Nie należy używać `Preview` w kodzie produkcyjnym, ponieważ jest on przeznaczony do debugowania i może obniżyć wydajność.

Proces konstruowania modelu jest eksperymentalny i iteracyjny. Aby sprawdzić, jakie dane będą wyglądały po przetworzeniu wstępnego przetwarzania lub uczeniu modelu uczenia maszynowego na podzestawie danych, użyj [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview%2A) metody, która zwraca [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview) . Wynikiem jest obiekt z `ColumnView` i właściwości, `RowView` które są zarówno [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) i zawierają wartości w określonej kolumnie lub wierszu. Określ liczbę wierszy, do których mają zostać zastosowane przekształcenia z `maxRows` parametrem.

![Obiekt podglądu debugera danych](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

Wynik inspekcji [`IDataView`](xref:Microsoft.ML.IDataView) będzie wyglądać podobnie do poniższego:

![Widok wiersza podglądu debugera danych](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
