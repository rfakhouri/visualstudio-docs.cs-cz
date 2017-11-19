---
title: "Popisy událostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6ce3e623a2d1787aa67f8a6e4dcfcf9530e8766c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="event-descriptions"></a>Popisy událostí
Každý typ události má konkrétní účel.  
  
## <a name="events-and-the-reasons-for-their-use"></a>Události a důvody pro jejich používání  
  
|Událost|Popis|  
|-----------|-----------------|  
|Aktivovat události dokumentu|Nastane, když modul ladění (DE) chce IDE otevřít nebo přenést do popředí dokumentu.|  
|Vázané Breakpoint – nebo zarážek chybové události|Posílají, když je vázán zarážku nebo když zarážku nelze vytvořit vazbu a vrátí chybu.|  
|Breakpoint – nevázaných události|Nastane, když vázané breakpoint odpojuje z kódu.|  
|Události můžete zastavit.|Odeslán integrovaného vývojového prostředí pro určení, zda uživatel chcete zastavit v určitém bodě v kódu.|  
|Breakpoint – události|Nastane, když je dosáhl zarážku kód nebo data.|  
|Události textového dokumentu|Nastane, když se změní text v dokumentu. Tyto události se neodesílají prostřednictvím `IDebugEventCallBack2::Event` metoda.|  
|Události vytváření modulu|Odeslat při prvním vytvoření motoru.|  
|Vstupní bod události|Posílají, když program laděné byl spuštěn jeho inicializace kódu a bylo dosaženo jeho první vstupní bod uživatele.|  
|Události výjimky|Posílají, když se spuštěným programem přístupy k výjimce.|  
|Události dokončení vyhodnocení výrazu|Odeslána po dokončení vyhodnocení asynchronní výrazu.|  
|Vyhledejte události – Symbol|Odeslána vždy, když je DE je požádat uživatele o najít symboly pro modul.|  
|Dokončení události zatížení|Odešle jenom když je dokončena počáteční program zatížení a první kód bude spuštěn v programu.|  
|Zpráva události|Odeslat při odesílání zprávy pro uživatele.|  
|Události modulu zatížení|Posílají, když je načten nebo odpojeno nový modul.|  
|Výstupní řetězec události|Posílají, když program zapíše výstup ladění.|  
|Vytvoření a zrušení události|Odeslat oznamujeme vytvoření nebo odstranění procesy, programy, vlastností, relací a vláken, Visual Studio IDE můžete udržovat přehled o stavu programů laděné.|  
|Krok dokončení události|Posílají, když krok je dokončen.|  
|Název události změny vláken|Posílají, když uživatel změní název vlákna.|  
|Události změny název programu|Posílají, když uživatel změní název programu.|  
  
## <a name="see-also"></a>Viz také  
 [Odesílání událostí](../../extensibility/debugger/sending-events.md)