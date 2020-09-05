---
ms.openlocfilehash: cb9305f623044233082286863d2f2d2c7e9d665a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496816"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="caa66-101">Trwałość SQL przepływu pracy dodaje klastry kluczy podstawowych i nie zezwala na wartości null w niektórych kolumnach</span><span class="sxs-lookup"><span data-stu-id="caa66-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="caa66-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="caa66-102">Details</span></span>

<span data-ttu-id="caa66-103">Począwszy od .NET Framework 4,7, tabele utworzone dla magazynu wystąpienia przepływu pracy SQL (SWIS) przez skrypt SqlWorkflowInstanceStoreSchema. SQL używają klastrowanych kluczy podstawowych.</span><span class="sxs-lookup"><span data-stu-id="caa66-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="caa66-104">Z tego powodu tożsamości nie obsługują <code>null</code> wartości.</span><span class="sxs-lookup"><span data-stu-id="caa66-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="caa66-105">Ta zmiana nie ma wpływu na operację SWIS.</span><span class="sxs-lookup"><span data-stu-id="caa66-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="caa66-106">Wprowadzono aktualizacje obsługujące SQL Server replikację transakcyjną.</span><span class="sxs-lookup"><span data-stu-id="caa66-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="caa66-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="caa66-107">Suggestion</span></span>

<span data-ttu-id="caa66-108">Aby można było obsłużyć tę zmianę, należy zastosować plik SQL SqlWorkflowInstanceStoreSchemaUpgrade. SQL do istniejących instalacji.</span><span class="sxs-lookup"><span data-stu-id="caa66-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="caa66-109">Nowe instalacje baz danych zostaną automatycznie zmienione.</span><span class="sxs-lookup"><span data-stu-id="caa66-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="caa66-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="caa66-110">Name</span></span>    | <span data-ttu-id="caa66-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="caa66-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="caa66-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="caa66-112">Scope</span></span>   |<span data-ttu-id="caa66-113">Edge</span><span class="sxs-lookup"><span data-stu-id="caa66-113">Edge</span></span>|
|<span data-ttu-id="caa66-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="caa66-114">Version</span></span>|<span data-ttu-id="caa66-115">4,7</span><span class="sxs-lookup"><span data-stu-id="caa66-115">4.7</span></span>|
|<span data-ttu-id="caa66-116">Typ</span><span class="sxs-lookup"><span data-stu-id="caa66-116">Type</span></span>|<span data-ttu-id="caa66-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="caa66-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="caa66-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="caa66-118">Affected APIs</span></span>

<span data-ttu-id="caa66-119">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="caa66-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
