---
title: Možnosti, textový Editor HTML (webové formuláře), formátování
ms.date: 1/15/2019
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.HTML.Format
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 109c40bc555985efe4a305a749890dac0e2f7f22
ms.sourcegitcommit: d0b02affd24e66efed924c197824f35f823e3240
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/21/2019
ms.locfileid: "54417782"
---
# <a name="options-text-editor-html-web-forms-formatting"></a>Možnosti, textový Editor HTML (webové formuláře), formátování

Použití **formátování** možnosti stránky lze nastavit možnosti projektu HTML pro formátování kódu v editoru kódu. Pro přístup k této stránce, na panelu nabídek zvolte **nástroje** > **možnosti**a potom rozbalte **textový Editor** > **HTML (webové formuláře)**   >  **Formátování**.

## <a name="capitalization"></a>Malá a velká písmena

Když tyto možnosti jsou vybrané, zobrazení zdroje a editory XML platí pro názvy elementů a atributů nejdřív vytvořené elementy a během automatického formátování výchozí formátování. **Použít automatické formátování** nastavení určit čas v které automatického přeformátování vyvolá.

> [!WARNING]
> XML rozlišuje velká a malá písmena. Nastavení výchozí případ může mít vliv na analyzátory jazyka XML.

### <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

**Serverové značky, Server atributy**

Tyto možnosti určují, jak velké značky pro ovládací prvky webového serveru.

|Možnost|Výsledek|
|---------------------------------|------------------------------|
|**Jako vložené**|Element případem je stejným způsobem, jako je zadat.|
|**velká písmena**|Názvy elementů jsou přeformátována na velká písmena.|
|**Malá**|Názvy elementů jsou přeformátována na malá písmena.|
|**Definice sestavení**|Element případ je určeno v odpovídajícím typu třídy bude definován takhle elementu.|


**Značka klienta, atributy klienta**

Tyto možnosti určit, zda automatické formátování změní názvy atributů HTML a vlastnosti na velká nebo malá nebo zůstanou jako vložené.

|Možnost|Výsledek|
|---------------------------------|------------------------------|
|**Jako vložené**|Atribut případem je stejným způsobem, jako je zadat.|
|**velká písmena**|Názvy atributů jsou přeformátována na velká písmena.|
|**Malá**|Názvy atributů jsou přeformátována na malá písmena.|


## <a name="automatic-formatting-options"></a>Možnosti automatického formátování

Tyto možnosti způsobit zobrazení editoru zdrojového kódu s přidáváním a odebíráním zalomení během automatického formátování. Můžete také určit, zda editor přidá uvozovky kolem atributy.

> [!NOTE]
> Tato nastavení se nezmění mezer v rámci kód XML.

### <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

- **Při psaní vkládat uvozovky u hodnot atributů**

   Pokud je vybraná tato možnost, editor automaticky vloží atributů do uvozovek při psaní (například: ID = "Select1"). Pokud chcete vkládání uvozovek do vašeho kódu ručně, zrušte zaškrtnutí tohoto políčka.


   > [!NOTE]
   > Jestli je vybraná tato možnost, všechny existující uvozovky ve vašem kódu jsou zachovány; uvozovky jsou nikdy neodeberou.

- **Při formátování vkládat uvozovky u hodnot atributů**

   Pokud je vybraná tato možnost, automatického formátování přidá uvozovky kolem hodnot atributů (například: ID = "Select1").

   > [!NOTE]
   > Jestli je vybraná tato možnost, všechny existující uvozovky ve vašem kódu jsou zachovány.

- **Automatické vkládání uzavírací značky**

   Pokud je vybraná tato možnost, editoru automaticky vytvoří ukončovací značky (například  **\</b >**) při uzavření počáteční značka.

## <a name="tag-wrapping"></a>Obtékání značky

Tyto možnosti určují, zda editor rozdělí značky do řádků v případě, že jsou nad rámec určité délky.

### <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

- **Při překročení zadané délky Zalomit značky**

   Při výběru, editoru rozdělí značky na řádcích, pokud značka přesahuje délku zadáte **délka** textového pole. Tato akce dojde pouze v případě, že formátování značky, ne v případě, že píšete novou značku.

   > [!NOTE]
   > Hodnota, kterou zadáte, se používá jako minimální hodnota. Rozdělit editor jednotlivé atributy.

- **Délka**

   Určuje počet znaků, které mají zobrazit v řádku před zabalení. Toto vstupní pole je zakázáno, pokud **Sbalit značku, jestliže přesáhne určenou délku** je políčko zaškrtnuté.

- **Specifické nastavení značky**

   Zobrazí **specifické nastavení značky** dialogové okno, které umožňuje nastavit možnosti formátování pro jednotlivé značky nebo skupiny značek.

## <a name="see-also"></a>Viz také:

- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)