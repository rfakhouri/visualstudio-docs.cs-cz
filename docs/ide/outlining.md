---
title: Osnova | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- outlining
- Visual Studio, expand/collapse code
- Visual Studio, outlining
- expand/collapse code
- code [Visual Studio], outlining
- code [Visual Studio], hiding
- outlining code
ms.assetid: d1476758-9d35-4d74-b63c-310661932ecd
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cc1b41f0b1095876129a9be451e5a1ff774c8dc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="outlining"></a>Sbalování
Můžete skrýt nějaký kód ze zobrazení sbalením oblasti kód tak, aby se v části znaménko plus (+). Kliknutím na symbol plus rozbalíte sbalené oblast. (Nebo stisknout kombinaci kláves CTRL + M + M na sbalit oblast a potom CTRL + M + M a rozbalte ji znovu.) Můžete také sbalit oblast popisující poklepáním na kterýkoli řádek v oblasti na popisující okrajem, která se zobrazí vlevo kódu. Po přesunutí ukazatele myši sbalené oblast, můžete zobrazit obsah sbalené oblasti jako popisek.  
  
 Oblasti v popisující okraj jsou také vyznačené po přesunutí ukazatele myši okraj pomocí myši. Barva zvýraznění výchozí zdánlivě slabé místo v některých konfiguracích barev. Můžete změnit v **Nástroje/možnosti/prostředí/písma a barvy nebo Collapsible oblast**.  
  
 Pokud pracujete v popsané kódu, můžete rozbalit oddílů, které chcete pracovat, je sbalit, když jste hotovi a poté přesuňte do dalších částech. Pokud nechcete, aby tak, aby měl osnovy zobrazí, můžete použít **zastavit osnovy** příkaz k odebrání informace outline bez narušení vašeho kódu.  
  
 **Vrátit zpět** a **vrátit** příkazy **upravit** nabídky vliv tyto akce. **Kopie**, **Vyjmout**, **vložení**, a operací přetažení myší zachovat popisující informací, ale není stav sbalitelné oblasti. Například při kopírování oblasti, která sbalena, **vložit** operaci se vložit zkopírovaný text jako rozšířené oblast.  
  
> [!CAUTION]
>  Při změně oblast popsané osnovy mohou být ztraceny. Odstranění nebo najít a nahradit provozu může například vymazat konce oblasti.  
  
 Následující příkazy můžete najít na **úpravy nebo osnova** podnabídky.  
  
|||  
|-|-|  
|Skrýt výběr|(CTRL + M, CTRL + H) - sbalí vybraného bloku kódu, který obvykle nebude k dispozici pro osnovy, například `if` bloku. Chcete-li odebrat vlastní oblasti, použijte **zastavit skrytí aktuální** (nebo CTRL + M, CTRL + U). Není k dispozici v jazyce Visual Basic.|  
|Přepnutí osnovy rozšíření|-Obrátí aktuální stav skrytý nebo rozbalených nejvnitřnější osnovy části, když ukazatel leží vnořené sbalenou část.|  
|Přepněte všechny osnovy|(CTRL + M, CTRL + L) - nastaví všechny oblasti na stejnou sbalené nebo rozbalit stavu. Pokud jsou některé oblasti rozšířit a některé sbalené, pak sbalené rozbaleny regionů.|  
|Zastavit osnovy|(CTRL + M, CTRL + P) – Odebere popisující informací pro celý dokument.|  
|Zastavit skrytí aktuální|(CTRL + M, CTRL + U) – Odebere popisující informací pro aktuálně vybrané oblasti definovaný uživatelem. Není k dispozici v jazyce Visual Basic.|  
|Sbalit do definice|(CTRL + M, CTRL + O) - sbalí všechny typy členů.|  
|Blokování Sbalit:\<logické hraniční >|(Visual C++) Sbalí oblast, ve kterém je umístěn kurzor funkci. Například pokud kurzor se nachází uvnitř smyčku, smyčky je skrytá.|  
|Sbalit vše na: \<logické struktury >|(Visual C++) Sbalí všechny struktury uvnitř funkce.|  
  
 Visual Studio SDK můžete použít také k definování text oblastí, které chcete rozbalit nebo sbalit. V tématu [návod: vytvoření přehledu](../extensibility/walkthrough-outlining.md).