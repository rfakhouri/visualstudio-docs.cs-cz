---
title: "Ukázka rozhraní Komunikátoru Excel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: dd7db85df6e63869550cea579a894defd7be39b2
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="sample-excel-communicator-interface"></a>Ukázka rozhraní komunikátoru Excel
Ukázka `IExcelUICommunication` rozhraní se používá v `ExcelUICommunicator` objekt v `ExcelAddIn` projektu.  
  
## <a name="iexceluicommunication-interface"></a>IExcelUICommunication rozhraní  
 Toto rozhraní definuje body komunikace mezi `CodedUIExtension`, která se spouští v procesu programového testu uživatelského rozhraní a `ExcelCodedUIAddIn`, která se spouští v [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] procesu.  
  
 `ExcelCodedUIAddinHelper` Obsahuje sestavení `ExcelUICommunicator` třídu, která je odvozena z tohoto rozhraní a ke zpracování metody používá model objektů aplikace Excel.  
  
 Některé metody získat požadované informace z aplikace Excel potom vytvořit a vrátí jednu z informace objekty, například `CellInformation` objektu.  
  
 Ostatní metody pomocí zadaných informací objektu, najít odpovídající ovládacího prvku v aplikaci Excel a provádět některé proces na ovládací prvek. Například `ScrollIntoView` metoda posune listu tak, aby určené buňky.  
  
## <a name="codeduiextensibilitysample-and-excelcodeduiaddinhelper-communication"></a>CodedUIExtensibilitySample a ExcelCodedUIAddinHelper komunikace  
 `ExcelCodedUIAddinHelper` Sestavení běží v procesu aplikace Excel a má `UICommunicator` třídu, která implementuje `IExcelUITestCommunication` rozhraní a získá nebo nastaví požadované informace přímo z uživatelského rozhraní aplikace Excel.  
  
 `CodedUIExtensibilitySample` Sestavení běží v procesu Visual Studio programového testu uživatelského rozhraní. Toto sestavení obsahuje `Communicator` třídu, která otevře kanál .NET Remoting a poskytuje `Instance` vlastnost, která používá `IExcelUICommunication` rozhraní pro použití `UICommunicator` objekt v `ExcelCodedUIAddinHelper` sestavení k předávání žádostí a informace objekty, například `CellInformation` objektu přepínat mezi dvěma sestavení.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [Ukázka doplňku Excel pro programové testování uživatelského rozhraní](../test/sample-excel-add-in-for-coded-ui-testing.md)   
 [Ukázka rozšíření programového testu UI pro Excel](../test/sample-coded-ui-test-extension-for-excel.md)
