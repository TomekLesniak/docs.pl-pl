---
title: 'Przykładowy plik XML: Konfiguracja testu — LINQ to XML'
description: Ten plik XML, który jest używany w przykładach — zawiera dane konfiguracji testu.
ms.date: 07/20/2015
ms.assetid: 45bfb509-c1d4-4b4f-9690-1cb0c9816516
ms.openlocfilehash: f9e5d26d3bbdd70b304356cd3282d81d0687333a
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553451"
---
# <a name="sample-xml-file-test-configuration-linq-to-xml"></a><span data-ttu-id="e4ae6-103">Przykładowy plik XML: Konfiguracja testu (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="e4ae6-103">Sample XML file: Test configuration (LINQ to XML)</span></span>

<span data-ttu-id="e4ae6-104">Poniższy plik XML jest używany w różnych przykładach w dokumentacji LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="e4ae6-104">The following XML file is used in various examples in the LINQ to XML documentation.</span></span> <span data-ttu-id="e4ae6-105">To jest plik konfiguracji testu.</span><span class="sxs-lookup"><span data-stu-id="e4ae6-105">This is a test configuration file.</span></span>

## <a name="testconfigxml"></a><span data-ttu-id="e4ae6-106">TestConfig.xml</span><span class="sxs-lookup"><span data-stu-id="e4ae6-106">TestConfig.xml</span></span>

```xml
<?xml version="1.0"?>
<Tests>
  <Test TestId="0001" TestType="CMD">
    <Name>Convert number to string</Name>
    <CommandLine>Examp1.EXE</CommandLine>
    <Input>1</Input>
    <Output>One</Output>
  </Test>
  <Test TestId="0002" TestType="CMD">
    <Name>Find succeeding characters</Name>
    <CommandLine>Examp2.EXE</CommandLine>
    <Input>abc</Input>
    <Output>def</Output>
  </Test>
  <Test TestId="0003" TestType="GUI">
    <Name>Convert multiple numbers to strings</Name>
    <CommandLine>Examp2.EXE /Verbose</CommandLine>
    <Input>123</Input>
    <Output>One Two Three</Output>
  </Test>
  <Test TestId="0004" TestType="GUI">
    <Name>Find correlated key</Name>
    <CommandLine>Examp3.EXE</CommandLine>
    <Input>a1</Input>
    <Output>b1</Output>
  </Test>
  <Test TestId="0005" TestType="GUI">
    <Name>Count characters</Name>
    <CommandLine>FinalExamp.EXE</CommandLine>
    <Input>This is a test</Input>
    <Output>14</Output>
  </Test>
  <Test TestId="0006" TestType="GUI">
    <Name>Another Test</Name>
    <CommandLine>Examp2.EXE</CommandLine>
    <Input>Test Input</Input>
    <Output>10</Output>
  </Test>
</Tests>
```
