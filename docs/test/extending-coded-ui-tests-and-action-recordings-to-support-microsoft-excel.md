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
ms.openlocfilehash: bc4e500c401c148f9eb01c1dedd56f89ba534df8
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692054"
---
# <a name="extend-coded-ui-tests-and-action-recordings"></a>Rozšíření programových testů uživatelského rozhraní a zaznamenávání akcí

Testování framework pro programové testy uživatelského rozhraní a zaznamenávání akcí nepodporuje všechny možné uživatelské rozhraní. Nepodporuje specifické uživatelské rozhraní, který chcete otestovat. Například nelze vytvořit okamžitě programového testu UI nebo záznamu pro tabulky aplikace Microsoft Excel akce. Můžete však vytvořit vlastní rozšíření programového rozhraní testu uživatelského rozhraní, které podporuje vaše specifické uživatelské rozhraní a využívají k rozšiřitelnosti rozhraní programových testů uživatelského rozhraní.

![Architektura testu uživatelského rozhraní](../test/media/ui_testarch.png)

## <a name="sample-extension-to-test-microsoft-excel"></a>Ukázka rozšíření k testování aplikace Microsoft Excel

To [příspěvku na blogu](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/3-introducing-sample-excel-extension/) obsahuje odkaz [ukázkové rozšíření](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Components.PostAttachments/00/09/94/38/24/ExcelPluginSample.zip) pro rozhraní programových testů uživatelského rozhraní. Můžete také zobrazit celý [řady příspěvek blogu pro programové uživatelského rozhraní otestovat rozšiřitelnost](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/series-on-coded-ui-test-extensibility/).

> [!NOTE]
> Ukázka je určena pro použití s Microsoft Excel 2010. Může nebo nemusí fungovat s jinými verzemi aplikace Excel.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Doporučené postupy pro programové testy UI](../test/best-practices-for-coded-ui-tests.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)