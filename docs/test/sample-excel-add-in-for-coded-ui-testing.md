---
title: Ukázka doplňku Excel pro programové testování uživatelského rozhraní
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
helpviewer_keywords:
- coded UI tests, Excel Add-in sample
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a7d9c2e4e73ab2695f49cdcbd6f9a903b5db3229
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>Ukázka doplňku Excel pro programové testování uživatelského rozhraní
Tato ukázka Add-In pro [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] je navržený speciálně pro podporu listů programových testů uživatelského rozhraní aplikace Excel, které jsou zaznamenány a spustit v Visual Studio Enterprise. Doplněk je vytvořená pomocí Visual Studio Tools pro sadu Office.

 Další informace o tom, jak vytvořit doplněk aplikace Excel najdete v tématu [návod: Add-in vytváření vaše první VSTO pro Excel](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f) nebo vyhledávání MSDN pro "aplikaci Excel Add-In".

 I když doplněk aplikace Excel není primární předmět této dokumentace rozšíření programového testu uživatelského rozhraní pro aplikaci Excel, může být užitečné několik komentáře.

 Důležité části doplněk:

-   `ThisAddIn`  Třídy – spravuje .NET Remoting kanál mezi `ExcelUICommunicator` a [ukázka programového uživatelského rozhraní Test rozšíření pro aplikaci Excel](../test/sample-coded-ui-test-extension-for-excel.md).

-   `ExcelCodedUIAddinHelper_TemporaryKey.pfx`  -Certifikát zabezpečení pro testování v doplňku.

-   `ExcelUICommunicator`  Tato třída implementuje třídu - `IExcelUICommunication` rozhraní.

## <a name="thisaddin-class"></a>ThisAddIn – třída
 Většina této třídy je ve skutečnosti generovaný Visual Studio Tools for Office ve `ThisAddIn.Designer.cs` souboru při vytváření projektu doplněk aplikace Excel.

 Obslužné rutiny událostí jsou členy, které je nutné implementovat: `ThisAddIn_Startup()` a `ThisAddIn_Shutdown()`. Jejich účelem je inicializovat nebo zavřete .NET Remoting kanál, který je používán `ExcelUICommunicator`.

## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx
 Tento soubor obsahuje dočasné zabezpečení certifikát, který je generovaný Visual Studio Tools for Office a dává oprávnění sestavení Add-In k provozu v aplikaci Excel procesu pro testování Add-In a rozšíření. Tento certifikát, měli byste odstranit a buď vytvořit novou v **podpisování** Karta projektu **vlastnosti** okno, nebo připojení vlastního testování certifikátu.

## <a name="exceluicommunicator-class"></a>ExcelUICommunicator – třída
 Tato třída implementuje `IExcelUITestCommunication` rozhraní a získá požadované informace uživatelského rozhraní z model objektů aplikace Excel. Další informace najdete v tématu [ukázka rozhraní Komunikátoru Excel](../test/sample-excel-communicator-interface.md).

## <a name="see-also"></a>Viz také

- [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
- [Návod: Vytvoření prvního doplňku VSTO pro Excel](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)
- [Office a vývoj pro SharePoint](/office-dev/office-dev/office-and-sharepoint-development-in-visual-studio)
