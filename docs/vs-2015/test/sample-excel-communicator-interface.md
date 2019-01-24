---
title: Ukázka rozhraní Komunikátoru Excel | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 1dbf1090-762c-4824-82dd-2d7c2c6f00b6
caps.latest.revision: 13
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 42da15899bb9bab6388d32c87132796eff768d7e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54800014"
---
# <a name="sample-excel-communicator-interface"></a>Ukázka rozhraní komunikátoru Excel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ukázka `IExcelUICommunication` rozhraní se používá v `ExcelUICommunicator` objekt `ExcelAddIn` projektu.  
  
## <a name="iexceluicommunication-interface"></a>IExcelUICommunication Interface  
 Toto rozhraní definuje body komunikace mezi `CodedUIExtension`, která se spouští v procesu programový Test uživatelského rozhraní a `ExcelCodedUIAddIn`, která se spouští v [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] procesu.  
  
 `ExcelCodedUIAddinHelper` Obsahuje sestavení `ExcelUICommunicator` třídu, která je odvozena z tohoto rozhraní a používá model objektů aplikace Excel ke zpracování metody.  
  
 Některé metody získat požadované informace z aplikace Excel pak vytvořit a vrátí jednu z těchto objektů, jako `CellInformation` objektu.  
  
 Další metody použití objektu zadaných informací, najít odpovídající ovládací prvek v aplikaci Excel a provádějí některé procesy na ovládacím prvku. Například `ScrollIntoView` metoda posune listu tak, aby určené buňky.  
  
## <a name="codeduiextensibilitysample-and-excelcodeduiaddinhelper-communication"></a>CodedUIExtensibilitySample a ExcelCodedUIAddinHelper komunikace  
 `ExcelCodedUIAddinHelper` Sestavení běží v procesu Excelu a má `UICommunicator` třídu, která implementuje `IExcelUITestCommunication` rozhraní a získá nebo nastaví požadované informace přímo z uživatelského rozhraní aplikace Excel.  
  
 `CodedUIExtensibilitySample` Sestavení běží v procesu Visual Studio programový Test uživatelského rozhraní. Toto sestavení obsahuje `Communicator` třídu, která otevře kanál vzdálené komunikace .NET a poskytuje `Instance` vlastnost, která používá `IExcelUICommunication` rozhraní `UICommunicator` objekt `ExcelCodedUIAddinHelper` sestavení, které chcete předat požadavky a informace objekty, například `CellInformation` objekt vpřed a zpět mezi dvěma sestaveními.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [Ukázka doplňku Excel pro programové testování uživatelského rozhraní](../test/sample-excel-add-in-for-coded-ui-testing.md)   
 [Ukázka rozšíření programového testu UI pro Excel](../test/sample-coded-ui-test-extension-for-excel.md)
