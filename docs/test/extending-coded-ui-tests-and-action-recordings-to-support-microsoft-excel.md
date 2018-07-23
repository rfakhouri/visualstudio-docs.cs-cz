---
title: Rozšíření programových testů uživatelského rozhraní a zaznamenávání akcí
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 97d49c44a2ab7b81a0241366ec9cc6e74401d6f5
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39180487"
---
# <a name="extend-coded-ui-tests-and-action-recordings"></a>Rozšíření programových testů UI a záznamů akcí

Testovací rozhraní pro programové testy uživatelského rozhraní a zaznamenávání akcí nepodporuje každé uživatelské rozhraní. To nemusí podporovat konkrétní uživatelské rozhraní, které chcete testovat. Například nelze vytvořit okamžitě programový test uživatelského rozhraní nebo záznam akce pro tabulky Microsoft Excel. Můžete však vytvořit vlastní rozšíření programového uživatelského rozhraní pro testování, která podporuje vaše konkrétní uživatelské rozhraní s využitím rozšíření programových testů uživatelského rozhraní.

![Architektura Test uživatelského rozhraní](../test/media/ui_testarch.png)

## <a name="sample-extension-to-test-microsoft-excel"></a>Ukázka rozšíření k testování aplikace Microsoft Excel

To [blogový příspěvek](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/3-introducing-sample-excel-extension/) obsahuje odkaz [ukázkové rozšíření](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Components.PostAttachments/00/09/94/38/24/ExcelPluginSample.zip) pro rozhraní programového testu uživatelského rozhraní. Můžete také zobrazit celý [řady příspěvek blogu pro kódované UI testování rozšíření](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/series-on-coded-ui-test-extensibility/).

> [!NOTE]
> Ukázka je určena pro použití s Microsoft Excel 2010. To může nebo nemusí fungovat s jinými verzemi aplikace Excel.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Osvědčené postupy pro programové testy uživatelského rozhraní](../test/best-practices-for-coded-ui-tests.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)