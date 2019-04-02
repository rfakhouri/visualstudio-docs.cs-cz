---
title: Okno vlastností
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- properties [Visual Studio], Properties Window
- handler functions, Properties window
- handlers, Properties window
- Windows messages
- properties [Visual Studio], setting at design time
- properties [Visual Studio], editing
- Property Browser
- Windows messages, adding message handlers
- Properties window, overrides
- virtual functions, Properties window
- Properties window
ms.assetid: e6e0fa4f-75c4-4a52-af15-281cd61876ca
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e26bd9d874ba5526a858e32907bff6676b68c81e
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790729"
---
# <a name="properties-window"></a>Vlastnosti – okno

Toto okno k zobrazení a změna vlastností návrhu a událostí vybraných objektů, které se nacházejí v editorech a návrhářích. Můžete také použít **vlastnosti** okna k úpravám a zobrazování souborů, projektů a vlastností řešení. Můžete najít **vlastnosti** na okno **zobrazení** nabídky. Můžete ji také otevřít stisknutím kombinace kláves **F4** nebo pomocí klávesové zkratky **vlastnosti** do vyhledávacího pole.

**Vlastnosti** okno zobrazuje různé typy editačních polí v závislosti na potřebách určité vlastnosti. Tato editační pole zahrnout editační políčka, rozevírací seznamy a odkazy na vlastní editor dialogových oknech. Vlastnosti zobrazené šedě jsou jen pro čtení.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

Objekt name\
Zobrazí seznam aktuálně vybraný objekt nebo objekty. Jsou zobrazeny pouze objekty z aktivního editoru nebo návrháře. Když vyberete více objektů, zobrazí se pouze vlastnosti, které jsou společné pro všechny vybrané objekty.

Categorized\
Uvádí všechny vlastnosti a hodnoty vlastností pro vybraný objekt podle kategorie. Můžete sbalit kategorii a snížit počet viditelných vlastností. Když rozbalíte nebo sbalíte kategorii, zobrazí se znak plus (+) nebo minus (-) nalevo od názvu kategorie. Kategorie jsou uvedeny podle abecedy.

Alphabetical\
Seřadí podle abecedy všechny vlastnosti doby návrhu a události vybraných objektů. Chcete-li upravit nezašedlou vlastnost, klikněte na buňku napravo a zadejte změny.

Property Pages\
Zobrazí **stránky vlastností** dialogové okno nebo **Návrháře projektu** pro vybranou položku. Stránky vlastností zobrazí podmnožinu, stejnou nebo nadmnožinu vlastností dostupných v **vlastnosti** okna. Toto tlačítko slouží k zobrazení a úpravám vlastností vztahujících se k aktivní konfiguraci projektu.

Properties\
Zobrazí vlastnosti objektu. Mnoho objektů má také události, které lze zobrazit pomocí **vlastnosti** okna.

Seřadit podle vlastnosti Source\
Vlastnosti skupiny podle zdroje, jako je dědičnost, využívají styly a vazby. K dispozici pouze při úpravách souborů XAML v návrháři.

Events\
Zobrazí události objektu.

> [!NOTE]
> To **vlastnosti** ovládací prvek panelu nástrojů okna je pouze k dispozici, když je formulář nebo návrhář ovládacího prvku je aktivní v kontextu [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projektu. Při úpravách souborů XAML, události se zobrazí na samostatné kartě v okně Vlastnosti.

Messages\
Obsahuje seznam všech zpráv Windows. Umožňuje přidat nebo odstranit zadané funkce obslužné rutiny pro zprávy zadané pro vybranou třídu.

> [!NOTE]
> To **vlastnosti** ovládací prvek panelu nástrojů okna je k dispozici pouze při **zobrazení tříd** aktivní okno v kontextu [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projektu.

Overrides\
Obsahuje seznam všech virtuálních funkcí pro vybranou třídu a umožňuje přidat nebo odstranit přepisující funkce.

> [!NOTE]
> To **vlastnosti** ovládací prvek panelu nástrojů okna je k dispozici pouze při **zobrazení tříd** aktivní okno v kontextu [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projektu.

Popis pane\
Zobrazuje typ vlastnosti a krátký popis vlastnosti. Popis vlastnosti vypínat a zapínat pomocí příkazu popis v místní nabídce můžete vypnout.

> [!NOTE]
> To **vlastnosti** ovládací prvek panelu nástrojů okna není k dispozici při úpravách souborů XAML v návrháři.

Miniatura view\
Zobrazí vizuální znázornění aktuálně vybraného prvku při úpravách souborů XAML v návrháři.

Search\
Poskytuje funkce vyhledávání pro vlastnosti a události při úpravách souborů XAML v návrháři. Vyhledávací pole reaguje na částečné slovní vyhledávání a aktualizuje výsledky hledání během psaní.

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)