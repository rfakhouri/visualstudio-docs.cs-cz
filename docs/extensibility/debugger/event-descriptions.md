---
title: Popisy událostí | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 600d9576d72dbd36b5ff7c2a0d9f0333f72dfafa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101021"
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