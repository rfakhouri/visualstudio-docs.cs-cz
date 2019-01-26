---
title: Ikony zobrazení třídy a prohlížeče objektů
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- icons, in Object Browser
- signal icons
- Class View tool, symbols
- graphic symbols
- IntelliSense, icons
- icons, IntelliSense
- symbols, Object Browser icons
- Object Browser, icons in Class View
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3791c6b94f4c229efe843b463cb51a64998e5b6f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958248"
---
# <a name="class-view-and-object-browser-icons"></a>Ikony zobrazení tříd a prohlížeče objektů

**Zobrazení tříd** a **prohlížeče objektů** zobrazení ikon představující kód entity, například, obory názvů, třídy, funkce a proměnné. Následující tabulka ukazuje a popisuje ikony.

|Ikona|Popis|Ikona|Popis|
|----------|-----------------|----------|-----------------|
|![Namespace Symbol](../ide/media/vxnamespace_icon.gif)|Obor názvů|![Deklarace symbolu](../ide/media/vxmethod_icon.gif)|Metoda nebo funkce|
|![Ikona třídy](../ide/media/vxclass_icon.gif)|Třída|![Symbol operátoru](../ide/media/vxoperator_icon.gif)|Operátor|
|![Symbol rozhraní typu Lupa](../ide/media/vxinterface_icon.gif)|Rozhraní|![Vlastnost Symbol](../ide/media/vxproperty_icon.gif)|Vlastnost|
|![Struktura Symbol](../ide/media/vxstruct_icon.gif)|Struktura|![Ikona pole.](../ide/media/vxfield_icon.gif)|Pole nebo proměnné|
|![Sjednocení Symbol](../ide/media/vxunion_icon.gif)|Unie|![Symbol události](../ide/media/vxevent_icon.gif)|Událost|
|![Výčet – Symbol](../ide/media/vxenum_icon.gif)|Výčet|![Konstantní ikonu](../ide/media/vxconstant_icon.gif)|Konstanta|
|![Typ definice symbolu](../ide/media/vxtypedef_icon.gif)|Definice TypeDef|![Položka výčtu – Symbol](../ide/media/vxenumitem_icon.gif)|Položky výčtu|
|![Modul symbolů sady Visual Studio](../ide/media/vxmodule_icon.gif)|Modul|![Symbol položka mapování](../ide/media/vxmapitem_icon.gif)|Položka mapování|
|![Symbol – metoda rozšíření](../ide/media/extensionmethod.gif)|Metody rozšíření|![Deklarace symbolu](../ide/media/vxmethod_icon.gif)|Externí deklarace|
|![Delegát – Symbol](../ide/media/vxdelegate_icon.gif)|Delegát|![Ikona chyby pro zobrazení tříd a prohlížeče objektů](../ide/media/erroricon.gif)|Chyba|
|![Výjimka – Symbol](../ide/media/vxexception_icon.gif)|Výjimka|![Symbol šablony](../ide/media/vxtemplate_icon.gif)|Šablona|
|![Mapa – Symbol](../ide/media/vxmap_icon.gif)|Mapa|![Chyba vykřičník bodu](../ide/media/vxerror_icon.gif)|Neznámé|
|![Symbol předávání typu](../ide/media/ob_type_forward.gif)|Předávání typů|||

## <a name="signal-icons"></a>Signální ikony

Následující signální ikony platí pro všechny předchozí ikony a určit jejich přístupnost.

|Ikona|Popis|
|----------|-----------------|
|\<Žádná ikona signál >|Veřejné. Přístupná z libovolné místo v této komponentě a u každé komponenty, která na něj odkazuje.|
|![Signál chráněné Symbol](../ide/media/vxsignal_icon_key.gif)|Chráněné. Přístupné z obsažené třídy nebo typu nebo které pocházejí z obsahující třídy nebo typu.|
|![Signál soukromých symbolů](../ide/media/vxsignal_icon_lock.gif)|Privátní. Přístupný pouze v obsahující třídy nebo typu.|
|![Signál zapečetěné Symbol](../ide/media/vxsignal_icon_envelope.gif)|Zapečetěná.|
|![Signalizuje, že Friend&#47;interní Symbol](../ide/media/vxsignal_icon_diamond.gif)|Friend nebo interní. Přístupný pouze z projektu.|
|![Ikona šipky signálu](../ide/media/vxsignal_icon_arrow.gif)|Zástupce. Zástupce pro objekt.|

> [!NOTE]
> Pokud váš projekt je zahrnutý v databázi správy zdrojů, další signální ikony zobrazují označuje stav správy zdrojového kódu, například vráceny se změnami nebo rezervovány.

## <a name="see-also"></a>Viz také:

- [Zobrazení struktury kódu](../ide/viewing-the-structure-of-code.md)