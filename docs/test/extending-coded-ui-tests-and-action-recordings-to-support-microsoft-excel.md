---
title: Rozšíření programových testů uživatelského rozhraní a zaznamenávání akcí
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 71e5ae809cf2c42e032d8545f0007c61d97e7047
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53842161"
---
# <a name="extend-coded-ui-tests-and-action-recordings"></a>Rozšíření programových testů UI a záznamů akcí

Testovací rozhraní pro programové testy uživatelského rozhraní a zaznamenávání akcí nepodporuje každé uživatelské rozhraní. To nemusí podporovat konkrétní uživatelské rozhraní, které chcete testovat. Například nelze vytvořit okamžitě programový test uživatelského rozhraní nebo záznam akce pro tabulky Microsoft Excel. Můžete však vytvořit vlastní rozšíření programového uživatelského rozhraní pro testování, která podporuje vaše konkrétní uživatelské rozhraní s využitím rozšíření programových testů uživatelského rozhraní.

![Architektura Test uživatelského rozhraní](../test/media/ui_testarch.png)

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

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