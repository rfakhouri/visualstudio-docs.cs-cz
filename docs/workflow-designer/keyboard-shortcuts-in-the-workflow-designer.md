---
title: "Klávesové zkratky v Návrháři pracovních postupů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: WFDKeyboardShortcuts.UI
ms.assetid: 9be75438-a4a3-4781-94e5-45b7ec082358
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d720b3647b077cfe66950d842163d774cb34e92
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="keyboard-shortcuts-in-the-workflow-designer"></a>Klávesové zkratky v Návrháři pracovních postupů
Všechny základní funkce služby [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] přístupná pomocí klávesnice.  
  
## <a name="navigating-the-workflow-designer-using-the-keyboard"></a>Navigace návrháře pracovních postupů pomocí klávesnice  
 Uvnitř [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], globální zkratky a zkratky ladění týkají [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Navíc několik [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] konkrétní klávesové zkratky byly vytvořeny. V [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], můžete přemapovat všechny klávesové zkratky. Opětovné hostování nástroje aplikace, ale tyto klávesové zkratky jsou pevně zakódované.  
  
### <a name="workflow-designer-keyboard-shortcuts"></a>Klávesové zkratky v Návrháři pracovních postupů  
 Následující tabulka shrnuje výchozí klávesové zkratky, která je přiřazená [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] příkazy.  
  
|Zástupce|Účel|  
|--------------|-------------|  
|CTRL + E, A|Zobrazí nebo skryje Argument Designer.|  
|CTRL + E, C|Sbalí vybranou aktivitou na místě.|  
|CTRL + E, E|Rozšíří vybranou aktivitou na místě.|  
|CTRL + E, F|Připojí vybrané aktivity v vývojový diagram.|  
|CTRL + E, I|Zobrazí nebo skryje importy návrháře.|  
|CTRL + E, M|Přesouvá fokus klávesnice na další položku v pořadí.|  
|CTRL + E, N|Vytvoří novou proměnnou v oboru vybrané aktivity (nebo na nejbližší).|  
|CTRL + E, O|Zobrazit nebo skrýt mapu přehledu.|  
|CTRL + E, P|Přejde do nadřazené vybranou aktivitou. Tím přejde jednu úroveň v navigačním panelu s popisem cesty a změní kořenové aktivity na plochu návrháře.|  
|CTRL + E, S|Přidá položku s fokus klávesnice na aktuálně vybrané položky.|  
|CTRL + E, V|Zobrazí nebo skryje návrháře proměnné.|  
|CTRL + E, X|Rozbalí všechny aktivity v pracovním postupu.|  
|CTRL + ALT + F6|Přesune fokus klávesnice z aktuální oblasti uživatelského rozhraní další oblasti v sekvenci. Pořadí je následující:<br /><br /> 1.  Navigační panel s popisem cesty.<br />2.  Plochu návrháře<br />3.  Argumenty, proměnné nebo importy Návrhář Pokud otevřete<br />4.  Prostředí|  
  
### <a name="flowchart"></a>Vývojový diagram  
 V následujícím seznamu jsou gesta použitý k vytvoření vývojový diagram pomocí klávesnice. Jako zbytek [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], aktivity jsou přidány na plochu návrháře pomocí zástupce globální sady nástrojů součástí [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
-   Chcete-li přesunout aktivitu, vyberte aktivitu a použijte klávesy se šipkami do jiného umístění.  
  
-   Ke změně velikosti vývojový diagram, přesuňte aktivitu po aktuální ohraničení vývojový diagram pomocí klávesy se šipkami. Vývojový diagram je automaticky nastavena velikost.  
  
-   Pokud chcete nastavit aktivitu jako počáteční uzel, použijte **nastavit jako Počáteční_uzel** příkaz v místní nabídce.  
  
-   Připojení aktivity:  
  
    1.  Vyberte zdrojové aktivity pomocí klávesy tabulátor do aktivity.  
  
    2.  Stiskněte kombinaci kláves CTRL + E, M tolikrát, kolikrát podle potřeby přesunout fokus klávesnice k cílové aktivitě.  
  
    3.  Stisknutím kombinace kláves CTRL + E, chcete-li přidat cílové aktivitě výběru S.  
  
    4.  Stiskněte kombinaci kláves CTRL + E, F přidat konektor ze zdroje do cíle.  
  
 Poznámky o připojení aktivity pomocí klávesnice:  
  
-   Přidáním další aktivity výběru ještě před stisknutím klávesy CTRL + E, F. můžete nastavit víc připojení ve stejnou dobu Připojení jsou vytvářeny v pořadí, aktivity byly přidány do výběru.  
  
-   Pokud nemůže být připojen pár aktivity, například pokud zdrojové aktivity již odchozí připojení, jsou stále vytvořit další připojení mezi aktivitami ve výběru, kdykoli je to možné.  
  
-   Když **FlowDecision** je zahrnutá ve výběru a **FlowDecision** neobsahuje žádné výstupní spojnice, na které je umístěn konektor **True** větve.  
  
### <a name="expression-editing"></a>Úpravy výrazů  
 Ve výchozím nastavení, výchozí klávesové zkratky pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] úpravy textu použít uvnitř výrazu editor v [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], s těmito omezeními:  
  
-   Přemapování klávesové zkratky pro následující příkazy nemá žádný vliv. Výchozí klávesové zkratky můžete použít pouze pro přístup k tyto příkazy při úpravě výrazu.  
  
    1.  Vyjmout  
  
    2.  Kopírovat  
  
    3.  Vložit  
  
    4.  Vybrat vše  
  
    5.  Vrácení zpět  
  
    6.  Znovu:  
  
-   Přemapování klávesové zkratky pro úpravy příkazy uvnitř výrazu [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], upravit klávesové zkratky v [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] oboru. Změny provedené v textovém editoru oboru nelze použít automaticky na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Pokud chcete namapovat zástupce na obou místech, musíte použít změny dvakrát (jednou pro každý obor).