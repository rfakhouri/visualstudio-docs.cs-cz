---
title: Hledají se odkazy ve vašem kódu
ms.date: 09/26/2017
ms.topic: conceptual
helpviewer_keywords:
- code editor, find all references
- find all references
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0d49223d61e3c72f2726b89de99ba9c092ddefe
ms.sourcegitcommit: fd5a5b057df3d733f5224c305096907989811f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/18/2019
ms.locfileid: "67195255"
---
# <a name="find-references-in-your-code"></a>Hledání odkazů v kódu

Můžete použít **najít všechny odkazy** příkaz Najít, kde jsou prvky konkrétního kódu odkazovat v rámci vašeho základu kódu. **Najít všechny odkazy** příkaz je k dispozici v nabídce kontextu (klikněte pravým tlačítkem) elementu, který chcete vyhledat odkazy na. Nebo, pokud jste uživatelem klávesnice, stiskněte **Shift + F12**.

Výsledky se zobrazí v okně nástroje s názvem  **\<element > odkazy**, kde *element* je název položky, který hledáte. V panelu nástrojů **odkazy** okno umožňuje:
- Změňte rozsah vyhledávání v rozevíracím seznamu. Můžete hledat jenom v změněné dokumenty úplně až po celé řešení.
- Kopírovat vybrané položky odkazované výběrem **kopírování** tlačítko.
- Zvolte tlačítko Přejít na další nebo předchozí umístění v seznamu, nebo stisknutím klávesy **F8** a **Shift + F8** klíče Uděláte to tak.
- Odebere všechny filtry s vrácenými výsledky výběrem **vymazat všechny filtry** tlačítko.
- Změnit způsob vrácené položky jsou seskupeny výběrem nastavení v **Seskupit podle:** rozevíracího seznamu.
- Zachovat aktuální okno výsledků hledání výběrem **zachovat výsledky** tlačítko. Když vyberete toto tlačítko, aktuální výsledky hledání budete mít všechno pod toto okno a nové výsledky hledání zobrazeny v novém okně nástroje.
- Hledat řetězce ve výsledcích hledání tak, že zadáte text **vyhledávání, vyhledání všech odkazů** textového pole.

Můžete také ukazatele myši nad libovolný výsledek hledání pro zobrazení náhledu odkazu.

![Najít všechny odkazy na panelu nástrojů](../ide/media/vside_findallreferences.png)

## <a name="navigate-to-references"></a>Přejděte na odkazy
Přejděte na odkazy v můžete použít následující metody **odkazy** okno:

- Stisknutím klávesy **F8** přejít na další odkaz nebo **Shift + F8** přejít na předchozí odkaz.
- Stisknutím klávesy **Enter** klíče na odkaz nebo dvojím kliknutím ho, chcete-li přejít k němu v kódu.
- V nabídce klikněte pravým tlačítkem (kontextová nabídka) odkaz, zvolte **přejít na předchozí umístění** nebo **přejděte do následujícího umístění** příkazy.
- Zvolte **šipka nahoru** a **šipka dolů** klíčů (pokud jsou povoleny v **možnosti** dialogové okno). Chcete-li povolit tuto funkci na řádku nabídek zvolte **nástroje** > **možnosti** > **prostředí**  >   **Karty a Windows** > **kartu náhledu**a pak vyberte **povolit otevřen v kartě preview odeslání nových souborů** a **náhled vybraných souborů v Výsledky hledání** polí.

## <a name="change-reference-groupings"></a>Seskupení změn odkazu
Ve výchozím nastavení odkazy jsou seskupené podle projektu, pak podle definice. Toto seskupení pořadí však můžete změnit změnou nastavení v **Seskupit podle:** rozevíracího seznamu na panelu nástrojů. Například můžete změnit z výchozí nastavení **projekt a pak definice** k **definice a pak projekt**, i na další nastavení.

**Definice** a **projektu** se používají dvě výchozí skupiny, ale ostatní lze přidat kliknutím **seskupení** příkaz v nabídce klepněte pravým tlačítkem nebo kontextu vybranou položku. Přidání další seskupení může být užitečné, pokud má vaše řešení velké množství souborů a cesty.

## <a name="filter-by-reference-type-in-net"></a>Filtrovat podle typu odkazu v .NET
V C# nebo Visual Basic má okno Najít odkazy typu sloupce, kde uvádí typ odkazu nalezena. Filtrovat podle typu odkazu, kliknutím na ikonu filtru, který se zobrazí, když najede myší na záhlaví sloupce lze tento sloupec. Čtení, zápisu, odkazem, název, Namespace a typ se dá filtrovat odkazy.

![Najít odkazy na okno typ sloupce ](../ide/media/vside_findallreferencesKind.png)

## <a name="see-also"></a>Viz také:

- [Navigace v kódu](../ide/navigating-code.md)
