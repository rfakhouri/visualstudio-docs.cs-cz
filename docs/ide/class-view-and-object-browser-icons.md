---
title: "Třídy zobrazení a ikony v prohlížeči objekt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: caac984e7d281740c322d535bebe84032c15a38e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="class-view-and-object-browser-icons"></a>Ikony zobrazení třídy a prohlížeče objektů

**Třídy zobrazení** a **Prohlížeč objektů** zobrazit ikony, které představují entity kódu, například obory názvů, třídy, funkce a proměnné. Následující tabulka ukazuje a popisuje ikony.

|Ikona|Popis|Ikona|Popis|
|----------|-----------------|----------|-----------------|
|![Namespace Symbol](../ide/media/vxnamespace_icon.gif "vxNamespace_Icon")|Obor názvů|![Symbol deklarace](../ide/media/vxmethod_icon.gif "vxMethod_Icon")|Metody nebo funkce|
|![Třídy ikonu](../ide/media/vxclass_icon.gif "vxClass_Icon")|Třída|![Symbol operátoru](../ide/media/vxoperator_icon.gif "vxOperator_Icon")|Operátor|  
|![Rozhraní Symbol typu Lupa](../ide/media/vxinterface_icon.gif "vxInterface_Icon")|Rozhraní|![Vlastnost Symbol](../ide/media/vxproperty_icon.gif "vxProperty_Icon")|Vlastnost|
|![Struktury Symbol](../ide/media/vxstruct_icon.gif "vxStruct_Icon")|Struktura|![Ikona pole](../ide/media/vxfield_icon.gif "vxField_Icon")|Pole nebo proměnná|  
|![Union – Symbol](../ide/media/vxunion_icon.gif "vxUnion_Icon")|Unie|![Symbol událostí](../ide/media/vxevent_icon.gif "vxEvent_Icon")|Událost|  
|![Symbol – výčet](../ide/media/vxenum_icon.gif "vxEnum_Icon")|Výčet|![Konstantní ikonu](../ide/media/vxconstant_icon.gif "vxConstant_Icon")|Konstanta|  
|![Zadejte definici Symbol](../ide/media/vxtypedef_icon.gif "vxTypeDef_Icon")|Definice TypeDef|![Zobrazení výčtu Symbol položka](../ide/media/vxenumitem_icon.gif "vxEnumItem_Icon")|Položka výčtu|  
|![Visual Studio modulu Symbol](../ide/media/vxmodule_icon.gif "vxModule_Icon")|Modul|![Mapování položky Symbol](../ide/media/vxmapitem_icon.gif "vxMapItem_Icon")|Mapování položky|  
|![Symbol – metoda rozšíření](../ide/media/extensionmethod.gif "ExtensionMethod")|Metody rozšíření|![Symbol deklarace](../ide/media/vxmethod_icon.gif "vxMethod_Icon")|Externí deklarace|  
|![Delegovat Symbol](../ide/media/vxdelegate_icon.gif "vxDelegate_Icon")|Delegát|![Ikona chyby pro zobrazení tříd a prohlížeč objektů](../ide/media/erroricon.gif "ErrorIcon")|Chyba|  
|![Výjimka Symbol](../ide/media/vxexception_icon.gif "vxException_Icon")|Výjimka|![Symbol šablony](../ide/media/vxtemplate_icon.gif "vxTemplate_Icon")|Šablony|  
|![Map – Symbol](../ide/media/vxmap_icon.gif "vxMap_Icon")|mapy|![Chyba vykřičník Symbol](../ide/media/vxerror_icon.gif "vxError_Icon")|Neznámé|  
|![Zadejte přesměrování Symbol](../ide/media/ob_type_forward.gif "ob_type_forward")|Předávání typů|||  

## <a name="signal-icons"></a>Signální ikony

Následující signální ikony platí pro všechny předchozí ikony a určit jejich usnadnění.

|Ikona|Popis|
|----------|-----------------|  
|\<Žádná ikona signál >|Veřejné. Přístupné z kdekoli v této komponentě a z libovolné součásti, které na ni odkazuje.|  
|![Signal – Symbol chráněné](../ide/media/vxsignal_icon_key.gif "vxSignal_Icon_Key")|Chráněný. Přístupné z obsahující třídy nebo typu nebo zařízení odvozené z obsahující třídy nebo typu.|  
|![Symbol signál privátní](../ide/media/vxsignal_icon_lock.gif "vxSignal_Icon_Lock")|Privátní. Přístupné pouze v obsahující třídy nebo typu.|  
|![Signal – Symbol zapečetěná](../ide/media/vxsignal_icon_envelope.gif "vxSignal_Icon_Envelope")|Zapečetěné.|  
|![Signál, přítele &#47; interní Symbol](../ide/media/vxsignal_icon_diamond.gif "vxSignal_Icon_Diamond")|Friend nebo interní. Dostupné jenom z projektu.|  
|![Signal – ikona šipky](../ide/media/vxsignal_icon_arrow.gif "vxSignal_Icon_Arrow")|Zástupce. Zástupce k objektu.|

> [!NOTE]
> Pokud zdrojové řízení databáze je součástí projektu, další signální ikony zobrazují označující stav zdrojového kódu, například změnami nebo rezervována.

## <a name="see-also"></a>Viz také

[Zobrazení struktury kódu](../ide/viewing-the-structure-of-code.md)