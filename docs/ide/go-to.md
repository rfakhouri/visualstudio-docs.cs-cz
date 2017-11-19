---
title: "Vyhledání kódu pomocí příkazů přejít na | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 509b2107-23d1-4fb3-987f-ab99ef45b72e
helpviewer_keywords:
- code editor, go to
- code editor, go to line
- go to line
- go to
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 15b222eaa3e03a44f99f64e86f9c88d125e41f98
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="find-code-using-go-to-commands"></a>Vyhledání kódu pomocí přejít na příkazy  
Visual Studio **přejít na** příkazy zaměřují se hledání kódu můžete rychle najít zadané položky. Můžete přejít na konkrétní řádku, typ, symbol, souboru a člena z jednoduchého jednotné rozhraní. Tato funkce existuje v Visual Studio 2017 nebo novější.  

### <a name="how-to-use-it"></a>Způsobu jeho použití  

Vstup        | Funkce 
------------ | ---
**Klávesnice** | Stiskněte klávesu **Ctrl + t** nebo **Ctrl +,**     
**Myš**    | Vyberte **upravit**, **přejít na**, **přejděte na všechny**  

Tato akce zobrazí v horní části malém okně napravo od editoru kódu ve výchozím nastavení.  

![Přejděte na všechny](media/gotoall.png)

Při psaní do textového pole, výsledky se zobrazí v rozevíracím seznamu pod textové pole. Přejít na element, vyberte ho v seznamu.    

![Přejděte do okna](../ide/media/vside_navigatetowindow.png "přejít na okna")  

Můžete také zadat otazník (?) zobrazíte další nápovědu.  

  ![Přejděte na všechny nápovědy](media/gotoall_help.png)

### <a name="filtered-searches"></a>Filtrované hledání  
Ve výchozím nastavení je zadaná položka hledán v všechny položky řešení. Hledání kódu tak, aby specifické typy elementů však můžete omezit pomocí zahájením literálu hledané výrazy s určitých znaků. Výběrem tlačítka na panelu přejděte do dialogu nástrojů pole můžete také rychle změnit vyhledávací filtr. Tlačítka, které změnit typ filtry jsou na levé straně a tlačítka, které změnit rozsah vyhledávání se na pravé straně.  

![Přejděte na členy](../ide/media/vside_navigation_toolbar.png)

#### <a name="filter-to-a-specific-type-of-code-element"></a>Filtrovat na konkrétní typ. element kódu  
Chcete-li zúžit hledání tak, aby určitý typ element kódu, můžete do vyhledávacího pole zadejte předponu nebo vyberte jednu z pěti ikony filtru:  

Předpona | Ikona | Zástupce | Popis
:----: | ---- | -------- | ---
\#      | ![Ikona symbol](media/gotoall_symbolicon.png) | CTRL + 1, Ctrl + S | Přejděte na zadaný symbol
F      | ![Soubor ikony](media/gotoall_fileicon.png)     | CTRL + 1, Ctrl + F | Přejděte do určeného souboru
m      | ![Ikona členu](media/gotoall_membericon.png) | CTRL + 1, Ctrl + M | Přejděte k zadanému členu
t      | ![Ikony typu](media/gotoall_typeicon.png)     | CTRL + 1, Ctrl + T | Přejděte na zadaný typ.
:      | ![Ikona čáry](media/gotoall_lineicon.png)     | Ctrl+G         | Přejděte na zadané číslo řádku

#### <a name="filter-to-a-specific-location"></a>Filtrovat na konkrétní umístění    
Upřesněte hledání do určitého umístění, vyberte jednu z ikon dvě dokumentu:  

Ikona | Popis
---- | ---
![Aktuální dokumentu](media/gotoall_currentdocument.png) | Prohledat pouze aktuální dokument
![Externí dokumenty](media/gotoall_external.png) | Vyhledávání externí dokumentů kromě těch, které umístěný v projekt nebo řešení  

### <a name="camel-casing"></a>CamelCase  
Pokud používáte [camelCase](https://en.wikipedia.org/wiki/Camel_case) ve vašem kódu můžete najít elementy kódu rychlejší zadáním velkých písmen názvu element kódu. Například, pokud má váš kód typu s názvem `CredentialViewModel`, hledání můžete zúžit výběr typu filtru ("t") a pak zadáním stejně velkých písmen názvu (`CVM`) v dialogovém okně Přejít na. Tato funkce může být užitečné, pokud má váš kód dlouhé názvy.  

![Přejděte do okna - hledání s kapitálek](../ide/media/vside_capitalsearch.png)

### <a name="settings"></a>Nastavení  
Vyberte ikonu zařízení ![Ikona zařízení](media/gotoall_gear.png) Umožňuje změnit, jak tato funkce funguje:  

Nastavení | Popis
------- | ---
Karta náhled použití | Ihned zobrazit vybranou položku v karta Náhled prostředí IDE
Zobrazit podrobnosti    | V okně zobrazit projektu, soubor, řádku a souhrnné informace z dokumentační komentáře
Okno centra   | Přesuňte toto okno k centru horní části editoru kódu, místo pravé horní   

## <a name="see-also"></a>Viz také  
[Navigace v kódu](../ide/navigating-code.md)  
[Přejděte do definice a funkce Náhled definice](../ide/go-to-and-peek-definition.md)  