---
title: Fragmenty kódu
description: Jak efektivně programovat v sadě Visual Studio for Mac pomocí fragmentů kódu
author: conceptdev
ms.author: crdun
ms.date: 02/07/2019
ms.assetid: 0FE27C0C-A861-4133-A74E-8D0505CF5342
ms.openlocfilehash: 56f736aa1e32530b1db96ad301091151731b7d28
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62540043"
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu, často označuje jako kód _kód šablony_, jsou užitečné pro efektivní programování, protože umožňují vkládání a úpravy předpřipravené bloky kódu. Používání fragmentů kódu může být vhodné pro rychlé přidání běžných vzorů nebo dokonce pro výuku nová schémata Pokud jako vývojář si nejste jisti syntaxe. Nejsou k dispozici pro šablony C#, F#, HTML, XML, Python a syntaxe Razor.

Tato část vysvětluje, jak vytvářet, vkládat a používání fragmentů kódu.

## <a name="inserting-a-snippet"></a>Fragment kódu pro vložení

Existují některé jiné způsoby, jak přidat fragmenty kódu, z nichž některé jsou popsané níže:

- **Karta rozšíření** &ndash; začněte psát název šablony, vyberte ji ze seznamu a stiskněte klávesu **kartu**, **kartu** a přidejte ji:

  ![Karta rozšíření v kódu](media/source-editor-image13.png)

- **Panel nástrojů** &ndash; použít panel nástrojů pro zobrazení seznamu všech fragmentů kódu. Přetáhněte libovolné šabloně z panelu nástrojů na správné místo ve zdrojovém kódu:

  [![Fragmenty kódu v sadě nástrojů](media/source-editor-image14-sml.png)](media/source-editor-image14.png#lightbox)

- **Vložit šablony příkaz** &ndash; aktuálně nejsou k dispozici žádné výchozí klíč vazby sady pro vkládání šablony. Chcete-li jeden vytvořit, přejděte na **sady Visual Studio > Předvolby > vazeb klíče** a vyhledejte `template`. To umožňuje přidání požadovaného vazbu klíče do pole Upravit vazby, pak klikněte na tlačítko **použít**:

  ![Příkaz vložené šablony](media/source-editor-image15.png)

## <a name="creating-a-new-template"></a>Vytvoření nové šablony

I když existují mnoho existujících šablon v nejrůznějších jazycích, které můžete použít a upravit, nové šablony lze také přidat tak, že přejdete do **sady Visual Studio > Předvolby > textový Editor > fragmenty kódu**:

![Nová šablona Inset](media/source-editor-image12.png)

Stisknutím klávesy **přidat** nebo **upravit** tlačítka pro vytvoření nebo úprava fragmenty kódu.

## <a name="keywords-in-code-snippets"></a>Klíčová slova ve fragmentech kódu

Po vložení fragmentu kódu v editoru, definované klíčová slova jsou zvýrazněny a může upravit tabulátor mezi nimi. Klíčová slova se chovat jako "proměnné" ve fragmentu kódu, jsou definována tak, že znak dolaru `$` před a za názvem z klíčového slova. 

**Úpravy šablony** okno je uveden níže, úpravy předdefinované `prop` fragment kódu. Fragment kódu obsahuje dvě klíčová slova &ndash; `$type$` a `$name$` &ndash; který může mít nastavenou vlastnost další (například výchozí hodnota a popis) na pravé straně okna:

![Okno šablony](media/source-editor-image12z.png)

Následující pole se používají k definování fragment kódu:

- **Místní** &ndash; text uživatel zadává fragment kódu vložit.
- **Skupiny** &ndash; fragmenty jsou seskupené dohromady v nabídce obsahu fragmentu kódu pomocí této hodnoty.
- **Popis** &ndash; vysvětlení účelu v tomto fragmentu kódu.
- **MIME** &ndash; řídí, jaké typy souborů je k dispozici v tomto fragmentu kódu.
- **Je rozšiřitelný šablona** &ndash; ověřte to je zaškrtnuté políčko tak, aby fragment kódu lze vložit na pozici kurzoru zadáním klávesovou zkratku.
- **Obklopit s šablonou je** &ndash; zaškrtnutím tohoto políčka se tento zástupce v seznamu **obklopit fragmentem...**  kontextové nabídky v editoru.
- **Text šablony** &ndash; skutečný fragment kódu, který se vloží do editoru. Zástupné symboly – klíčové slovo lze definovat obklopením token se znaky dolaru, např. `$type$`.
- **Panel vlastností – klíčové slovo** &ndash; na pravé straně okna, pomocí rozevíracího seznamu v horní části zvolte klíčové slovo (třeba `type`) a upravit vlastnosti, jako je výchozí hodnota a popis.

## <a name="using-keywords-in-the-editor"></a>Pomocí klíčových slov v editoru

Použití fragment kódu s klíčovými slovy, jako ten výše definované, zadejte místní a stiskněte klávesu **kartu** dvakrát, a na pozici kurzoru se vloží obsah fragment kódu:

![Vložený fragment kódu znázorňující klíčová slova](media/source-editor-image12a.png)

Stisknutím klávesy **kartu** klíč pro přesun mezi `object` a `MyProperty` přizpůsobení fragment kódu pro vaši třídu.

Klíčové slovo lze opakovat ve fragmentu kódu, jako je například to `for` příkladu si všimněte `$i$` – klíčové slovo se zobrazí 3 místech:

![Šablona fragmentu s opakovaných slov](media/source-editor-image12b.png)

Při použití v editoru **kartu** klíč Přepne mezi první `i` a `max`. Pokud můžete přepsat `i` s jiným názvem proměnné, budou aktualizovány všechny tři instance:

![Vložené: fragmentu kódu zobrazuje více klíčových slov](media/source-editor-image12c.png)

### <a name="reserved-keywords"></a>vyhrazená klíčová slova

Existují dvě vyhrazená klíčová slova, které můžete použít v fragment kódu:

- `$selected$` &ndash; Pokud má fragment kódu **je příkazu Obklopit s šablonou** zaškrtnutí toto klíčové slovo bude nahrazen text, který byl zvýrazněné v editoru, když byla vybrána fragmentu kódu.
- `$end$` &ndash; Když uživatel dokončil úpravy klíčových slov v fragment kódu, kurzor se umístí na umístění `$end$` – klíčové slovo.

`for` Fragmentu kódu v předchozí části je příkladem obou těchto vyhrazená klíčová slova.

Odkazovat [referenční informace k fragmentům kódu sady Visual Studio](/visualstudio/ide/code-snippets-schema-reference#keywords) Další informace.

## <a name="see-also"></a>Viz také:

- [Fragmenty kódu (Visual Studio na Windows)](/visualstudio/ide/code-snippets)