---
title: Visual Studio Help Viewer tabulka obsahu
ms.date: 11/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
f1_keywords:
- hv_contents
helpviewer_keywords:
- Help Viewer, table of contents filtering
- Help Viewer, Contents tab
- Contents tab [Help Viewer]
- table of contents filtering [Help Viewer]
ms.assetid: 8b98464d-2b05-4710-ad68-5647e78c6b7b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6e7d9ae19cb2a37c6fbf6595a7f3a39895d22190
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945750"
---
# <a name="how-to-find-topics-in-the-table-of-contents"></a>Postupy: hledání témat v obsahu

V **obsah** kartě obsahu (obsah) můžete použít k nalezení informací. Obsah je rozevírací seznam obsahující všechny témat v nainstalované knih. Usnadnění informace o tom, jak procházet obsahu najdete v tématu [klávesové zkratky (Help Viewer)](../ide/shortcut-keys-help-viewer.md).

> [!IMPORTANT]
> Obor témat v obsahu k dispozici, závisí na filtr, který jste vybrali.

## <a name="filter-the-toc"></a>Filtrování obsahu

Můžete filtrovat TOC Chcete-li zúžit rozsah témata, které se zobrazují v **obsah** kartě. Názvy se zobrazí v seznamu, pouze v případě, že obsahují kořenovém termín, který zadáte. Například pokud zadáte "řešení potíží" jako filtr, pouze tituly, které obsahují "řešení potíží s" nebo "řešení potíží" zobrazí. Uzly, jejichž názvy neobsahují termín jsou sbaleny do jednoho uzlu se třemi tečkami (**...** ).

1.  Vyberte **obsah** kartě.

2.  V **filtru obsah** textové pole, zadejte termín.

> [!NOTE]
> Pokud filtr trvá dlouhou dobu spuštění, můžete zobrazit výsledky rychleji pomocí `title:` operátor rozšířené vyhledávání.

## <a name="synchronize-a-topic-with-the-toc"></a>Synchronizovat téma s obsahu

Pokud jste otevřeli pomocí indexu nebo funkce fulltextového vyhledávání téma, můžete určit, kde se toto téma je v obsahu synchronizace obsahu s okna tématu.

1.  Zobrazte téma.

2.  Klikněte **tématu zobrazit v obsah** na panelu nástrojů nebo stiskněte tlačítko **Ctrl**+**S**.

     **Obsah** kartě otevře a zobrazí v tématu umístění v obsahu.

## <a name="see-also"></a>Viz také

- [Postupy: hledání témat v rejstříku](../ide/how-to-find-topics-in-the-index.md)
- [Postupy: vyhledávání témat](../ide/how-to-search-for-topics.md)
- [Microsoft Help Viewer 2.2](../ide/microsoft-help-viewer.md)