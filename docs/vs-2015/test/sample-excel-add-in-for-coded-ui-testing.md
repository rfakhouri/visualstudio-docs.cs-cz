---
title: Ukázka doplňku Excel pro programové testování uživatelského rozhraní | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, Excel Add-in sample
ms.assetid: 2cd52d1a-4c35-43ca-8a84-9c79dabd907f
caps.latest.revision: 18
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ded54760efe611b337c736e0474042b70ff8bf2e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54791943"
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>Ukázka doplňku Excel pro programové testování uživatelského rozhraní
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato ukázka doplňku pro [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] je navržená speciálně pro podporu listů programové testy uživatelského rozhraní aplikace Excel, které se zaznamenávají a spustit v sadě Visual Studio Enterprise. Doplněk se vytvoří pomocí Visual Studio Tools for Office.  
  
 Další informace o tom, jak vytvořit Excel Add-In, naleznete v tématu [názorný postup: Vytvoření doplňku svůj první VSTO pro Excel](http://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f) nebo hledání MSDN pro "Excel Add-In".  
  
 I když Excelovém doplňku není primární předmět této dokumentace rozšíření programového testu UI pro Excel, množstvím komentářů může být užitečné.  
  
 Důležité části tohoto doplňku:  
  
-   `ThisAddIn`  Třída – spravuje Vzdálená komunikace .NET kanál mezi `ExcelUICommunicator` a [ukázka programového uživatelského rozhraní testu rozšíření pro aplikaci Excel](../test/sample-coded-ui-test-extension-for-excel.md).  
  
-   `ExcelCodedUIAddinHelper_TemporaryKey.pfx`  -Certifikát zabezpečení pro testování doplňku.  
  
-   `ExcelUICommunicator`  Tato třída implementuje třída – `IExcelUICommunication` rozhraní.  
  
## <a name="thisaddin-class"></a>Thisaddin – třída  
 Většinu této třídy je ve skutečnosti generované Visual Studio Tools for Office ve službě `ThisAddIn.Designer.cs` soubor při vytváření projektu doplňku aplikace Excel.  
  
 Obslužné rutiny událostí jsou členy, které je nutné implementovat: `ThisAddIn_Startup()` a `ThisAddIn_Shutdown()`. Jejich účelem je inicializovat nebo zavřete vzdálené komunikace .NET kanál, který je používán `ExcelUICommunicator`.  
  
## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx  
 Tento soubor obsahuje dočasný zabezpečení certifikát, který je generován Visual Studio Tools for Office a poskytuje oprávnění sestavení doplňku pracovat v procesu Excelu pro testování doplňky a rozšíření. Tento certifikát by měl odstranit a buď vytvořte nový **podepisování** kartu projektu **vlastnosti** okno, nebo připojit vlastní testování certifikátu.  
  
## <a name="exceluicommunicator-class"></a>Třída ExcelUICommunicator  
 Tato třída implementuje `IExcelUITestCommunication` rozhraní a získá požadované informace uživatelského rozhraní v objektovém modelu Excelu. Další informace najdete v tématu [ukázka rozhraní Komunikátoru Excel](../test/sample-excel-communicator-interface.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro Excel](http://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)   
 [Office a vývoj pro SharePoint](http://msdn.microsoft.com/library/2ddec047-263a-4901-a54c-a15fc8472329)
