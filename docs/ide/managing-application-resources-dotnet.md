---
title: Správa prostředků aplikace (.NET)
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- Resource Designer
- resources [Visual Studio]
- Resources page in Project Designer
- application resources [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1681484500c382b296a03e78661b808825768a5b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62538106"
---
# <a name="manage-application-resources-net"></a>Správa prostředků aplikace (.NET)

Zdrojové soubory jsou soubory, které jsou součástí aplikace, ale nejsou zkompilovány, pro soubory ikon příklad nebo zvukové soubory. Protože tyto soubory nejsou součástí procesu kompilace, můžete je změnit bez nutnosti znovu kompilovat vaše binární soubory. Pokud máte v úmyslu lokalizovat vaši aplikaci, měli byste použít soubory prostředků pro všechny řetězce a další prostředky, které je potřeba změnit, pokud lokalizovat vaši aplikaci.

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [Správa prostředků aplikace (Visual Studio for Mac)](/visualstudio/mac/managing-app-resources).

Další informace o prostředcích v desktopové aplikace .NET najdete v tématu [prostředky v desktopových aplikacích](/dotnet/framework/resources/index).

## <a name="work-with-resources"></a>Pracovat s prostředky

V spravovaný projekt kódu otevřete okno s vlastnostmi projektu. Otevřete okno Vlastnosti buď:

- Pravým tlačítkem myši na uzel projektu v **Průzkumníka řešení** a vyberete **vlastnosti**
- Zadáním **vlastnosti projektu** v **Ctrl**+**Q** vyhledávacího pole
- Výběr **Alt**+**zadejte** v **Průzkumníka řešení**

Vyberte **prostředky** kartu. Můžete přidat *RESX* souboru, pokud váš projekt není již obsahovat jednu, přidat a odstraňovat různé druhy prostředků a úpravám stávajících prostředků.

## <a name="resources-in-other-project-types"></a>Prostředky v jiných typů projektů

Prostředky se spravují odlišně v projektech .NET než v jiných typů projektů. Další informace o prostředcích v:

- Univerzální aplikace pro platformu Windows (UPW), najdete v článku [prostředků aplikace a systém správy zdrojů](/windows/uwp/app-resources/)
- Projekty C++, naleznete v tématu [práci se soubory prostředků](/cpp/windows/working-with-resource-files) a [jak: Vytvoření prostředku](/cpp/windows/how-to-create-a-resource)

## <a name="see-also"></a>Viz také:

- [Prostředky v aplikacích klasické pracovní plochy (.NET Framework)](/dotnet/framework/resources/index)
- [Správa prostředků aplikace (Visual Studio for Mac)](/visualstudio/mac/managing-app-resources)
