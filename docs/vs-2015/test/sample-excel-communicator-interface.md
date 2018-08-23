---
title: Ukázka rozhraní Komunikátoru Excel | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1dbf1090-762c-4824-82dd-2d7c2c6f00b6
caps.latest.revision: 13
ms.author: gewarren
manager: douge
ms.openlocfilehash: a1f544734cd00361162c461cd2b1682204075e10
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666158"
---
# <a name="sample-excel-communicator-interface"></a>Ukázka rozhraní komunikátoru Excel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ukázka rozhraní Komunikátoru Excel](https://docs.microsoft.com/visualstudio/test/sample-excel-communicator-interface).  
  
Ukázka `IExcelUICommunication` rozhraní se používá v `ExcelUICommunicator` objekt `ExcelAddIn` projektu.  
  
## <a name="iexceluicommunication-interface"></a>IExcelUICommunication rozhraní  
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



