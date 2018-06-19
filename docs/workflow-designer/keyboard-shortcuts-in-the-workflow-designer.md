---
title: Návrhář postupu provádění - klávesové zkratky v Návrháři pracovních postupů
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- WFDKeyboardShortcuts.UI
ms.assetid: 9be75438-a4a3-4781-94e5-45b7ec082358
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83664d6402c23da89adf332bc9cd34eac89384bb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977641"
---
# <a name="keyboard-shortcuts-in-the-workflow-designer"></a>Klávesové zkratky v Návrháři pracovních postupů

Všechny základní funkce návrháře pracovního postupu systému Windows byla přístupná pomocí klávesnice.

## <a name="navigating-the-workflow-designer-using-the-keyboard"></a>Navigace návrháře pracovních postupů pomocí klávesnice

V sadě Visual Studio 2010 globální zkratky a zkratky ladění použití návrháře pracovních postupů. Navíc byly vytvořeny počet konkrétní klávesové zkratky v Návrháři pracovních postupů. V sadě Visual Studio 2010 všechny klávesové zkratky můžete přemapovat. Opětovné hostování nástroje aplikace, ale tyto klávesové zkratky jsou pevně zakódované.

### <a name="workflow-designer-keyboard-shortcuts"></a>Klávesové zkratky v Návrháři pracovních postupů

Následující tabulka shrnuje výchozí klávesové zkratky, která je přiřazena k příkazům v Návrháři pracovních postupů.

|Zástupce|Účel|
|--------------|-------------|
|CTRL+E, A|Zobrazí nebo skryje Argument Designer.|
|CTRL+E, C|Sbalí vybranou aktivitou na místě.|
|CTRL+E, E|Rozšíří vybranou aktivitou na místě.|
|CTRL + E, F|Připojí vybrané aktivity v vývojový diagram.|
|CTRL + E, I|Zobrazí nebo skryje importy návrháře.|
|CTRL + E, M|Přesouvá fokus klávesnice na další položku v pořadí.|
|CTRL+E, N|Vytvoří novou proměnnou v oboru vybrané aktivity (nebo na nejbližší).|
|CTRL+E, O|Zobrazit nebo skrýt mapu přehledu.|
|CTRL + E, P|Přejde do nadřazené vybranou aktivitou. Tím přejde jednu úroveň v navigačním panelu s popisem cesty a změní kořenové aktivity na plochu návrháře.|
|CTRL + E, S|Přidá položku s fokus klávesnice na aktuálně vybrané položky.|
|CTRL+E, V|Zobrazí nebo skryje návrháře proměnné.|
|CTRL + E, X|Rozbalí všechny aktivity v pracovním postupu.|
|CTRL+ALT+F6|Přesune fokus klávesnice z aktuální oblasti uživatelského rozhraní další oblasti v sekvenci. Pořadí je následující:<br /><br /> 1.  Navigační panel s popisem cesty.<br />2.  Plochu návrháře<br />3.  Argumenty, proměnné nebo importy Návrhář Pokud otevřete<br />4.  Prostředí|

### <a name="flowchart"></a>Vývojový diagram

V následujícím seznamu jsou gesta použitý k vytvoření vývojový diagram pomocí klávesnice. Jako zbytek návrháře pracovních postupů se přidají aktivity na plochu návrháře pomocí zástupce globální sady nástrojů součástí sady Visual Studio 2010.

- Chcete-li přesunout aktivitu, vyberte aktivitu a použijte klávesy se šipkami do jiného umístění.

- Ke změně velikosti vývojový diagram, přesuňte aktivitu po aktuální ohraničení vývojový diagram pomocí klávesy se šipkami. Vývojový diagram je automaticky nastavena velikost.

- Pokud chcete nastavit aktivitu jako počáteční uzel, použijte **nastavit jako Počáteční_uzel** příkaz v místní nabídce.

- Připojení aktivity:

    1.  Vyberte zdrojové aktivity pomocí klávesy tabulátor do aktivity.

    2.  Stiskněte kombinaci kláves CTRL + E, M tolikrát, kolikrát podle potřeby přesunout fokus klávesnice k cílové aktivitě.

    3.  Stisknutím kombinace kláves CTRL + E, chcete-li přidat cílové aktivitě výběru S.

    4.  Stiskněte kombinaci kláves CTRL + E, F přidat konektor ze zdroje do cíle.

Poznámky o připojení aktivity pomocí klávesnice:

- Přidáním další aktivity výběru ještě před stisknutím klávesy CTRL + E, F. můžete nastavit víc připojení ve stejnou dobu Připojení jsou vytvářeny v pořadí, aktivity byly přidány do výběru.

- Pokud nemůže být připojen pár aktivity, například pokud zdrojové aktivity již odchozí připojení, jsou stále vytvořit další připojení mezi aktivitami ve výběru, kdykoli je to možné.

- Když **FlowDecision** je zahrnutá ve výběru a **FlowDecision** neobsahuje žádné výstupní spojnice, na které je umístěn konektor **True** větve.

### <a name="expression-editing"></a>Úpravy výrazů

Ve výchozím nastavení použít výchozí klávesové zkratky pro Visual Basic úpravy textu v editoru výrazu v Návrháři pracovních postupů, s těmito omezeními:

- Přemapování klávesové zkratky pro následující příkazy nemá žádný vliv. Výchozí klávesové zkratky můžete použít pouze pro přístup k tyto příkazy při úpravě výrazu.

   - Vyjmout
   - Kopírovat
   - Vložit
   - Vybrat vše
   - vrácení zpět
   - znovu:

- Pokud chcete přemapovat klávesové zkratky pro příkazy pro úpravy výrazu v Návrháři pracovních postupů v sadě Visual Studio 2010, upravte zástupce v oboru pracovního postupu návrháře. Změny provedené v textovém editoru oboru automaticky nevztahují na návrháře pracovních postupů. Pokud chcete namapovat zástupce na obou místech, musíte použít změny dvakrát (jednou pro každý obor).