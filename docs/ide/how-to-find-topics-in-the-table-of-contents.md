---
title: Pomocí aplikace Help Viewer obsah
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
ms.openlocfilehash: 86e334fac2fca09514dd4adaf4a05fac0accc11f
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2018
ms.locfileid: "53063406"
---
# <a name="how-to-find-topics-in-the-table-of-contents"></a>Postupy: hledání témat v obsahu

V **obsah** kartu, můžete použít obsah (TOC) k nalezení informací o. Obsah je rozšiřitelný seznam, který obsahuje všechna témata v nainstalovaných knihách. Usnadnění informace o tom, jak procházení obsahu naleznete v tématu [klávesové zkratky (Help Viewer)](../ide/shortcut-keys-help-viewer.md).

> [!IMPORTANT]
> Rozsah témat dostupných v obsahu závisí na filtru, který jste vybrali.

## <a name="filter-the-toc"></a>Filtrování obsahu

Můžete filtrovat-li zúžit rozsah témat, která se zobrazí v obsahu **obsah** kartu. Zobrazí v seznamu jenom v případě, že obsahují kořen termínu, který zadáte. Například pokud zadáte "problém" jako filtr, pouze produkty, které obsahují text "problém" nebo "problém" zobrazí. Uzly, jejichž nadpisy neobsahují daný výraz, jsou sbaleny do jednoho uzlu se třemi tečkami (**...** ).

1.  Zvolte **obsah** kartu.

2.  V **filtrovat obsahy** text zadejte termín.

> [!NOTE]
> Pokud filtru trvá dlouhou dobu spuštění, můžete zobrazit výsledky rychleji pomocí `title:` operátoru pro rozšířené hledání.

## <a name="synchronize-a-topic-with-the-toc"></a>Synchronizace tématu s obsahem

Pokud jste otevřeli téma pomocí rejstříku nebo funkcí fulltextového vyhledávání, můžete určit, kde je v tomto tématu v obsahu pomocí synchronizace obsahu s oknem tématu.

1.  Zobrazte téma.

2.  Klikněte na tlačítko **zobrazit téma v obsahu** tlačítko na panelu nástrojů nebo stisknete klávesu **Ctrl**+**S**.

     **Obsah** kartě se otevře a zobrazí se umístění tématu v obsahu.

## <a name="see-also"></a>Viz také:

- [Postupy: hledání témat v rejstříku](../ide/how-to-find-topics-in-the-index.md)
- [Postupy: vyhledávání témat](../ide/how-to-search-for-topics.md)
- [Microsoft Help Viewer 2.2](../ide/microsoft-help-viewer.md)