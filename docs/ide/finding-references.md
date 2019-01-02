---
title: Hledají se odkazy ve vašem kódu
ms.date: 09/26/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- code editor, find all references
- find all references
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f1e1e01721ae261b756bd6f3567b8f06dc73f12
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53921335"
---
# <a name="find-references-in-your-code"></a>Hledání odkazů v kódu

Můžete použít **najít všechny odkazy** příkaz Najít, kde jsou prvky konkrétního kódu odkazovat v rámci vašeho základu kódu. **Najít všechny odkazy** příkaz je k dispozici v nabídce kontextu (klikněte pravým tlačítkem) elementu, který chcete vyhledat odkazy na. Nebo, pokud jste uživatelem klávesnice, stiskněte **Shift + F12**.

Výsledky se zobrazí v okně nástroje s názvem  **<element> odkazy**, kde *element* je název položky, který hledáte. V panelu nástrojů **odkazy** okno umožňuje:
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
- V kontextové nabídce odkaz, zvolte **přejít na předchozí umístění** nebo **přejděte do následujícího umístění** příkazy.
- Zvolte **šipka nahoru** a **šipka dolů** klíčů (pokud jsou povoleny v **možnosti** dialogové okno). Chcete-li povolit tuto funkci na řádku nabídek zvolte **nástroje** > **možnosti** > **prostředí**  >   **Karty a Windows** > **kartu náhledu**a pak vyberte **povolit otevřen v kartě preview odeslání nových souborů** a **náhled vybraných souborů v Výsledky hledání** polí.

## <a name="change-reference-groupings"></a>Seskupení změn odkazu
Ve výchozím nastavení odkazy jsou seskupené podle projektu, pak podle definice. Toto seskupení pořadí však můžete změnit změnou nastavení v **Seskupit podle:** rozevíracího seznamu na panelu nástrojů. Například můžete změnit z výchozí nastavení **projekt a pak definice** k **definice a pak projekt**, i na další nastavení.

**Definice** a **projektu** se používají dvě výchozí skupiny, ale ostatní lze přidat kliknutím **seskupení** příkazu v místní nabídce vybranou položku. Přidání další seskupení může být užitečné, pokud má vaše řešení velké množství souborů a cesty.

## <a name="see-also"></a>Viz také:

- [Navigace v kódu](../ide/navigating-code.md)