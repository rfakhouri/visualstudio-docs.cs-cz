---
title: Popisy událostí | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5aff88047d6b1f79544af927751d7a053eeda218
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152824"
---
# <a name="event-descriptions"></a>Popisy událostí
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Každý typ události má konkrétní účel.  
  
## <a name="events-and-the-reasons-for-their-use"></a>Z důvodů pro jejich používání a události  
  
|Událost|Popis|  
|-----------|-----------------|  
|Aktivovat události dokumentu|Dojít, když chce ladicího stroje (DE) rozhraní IDE k otevření nebo dokumentu přenést do popředí.|  
|Vázaný zarážku nebo zarážku chybové události|Odesílá se, když je vázán na zarážku nebo když nelze svázat zarážku a vrátí chybu.|  
|Zarážka nevázaných události|Dojít, když vázaná zarážka odpojuje z kódu.|  
|Může dojít k zastavení událostí|Odeslat integrovaného vývojového prostředí k určení, zda uživatel chcete zastavit k určitému bodu v kódu.|  
|Události zarážky|Dojít při dosažení zarážky kód nebo data.|  
|Události textu dokumentu|Dojde ke změně textu v dokumentu. Tyto události se neodesílají prostřednictvím `IDebugEventCallBack2::Event` metody.|  
|Engine vytvoření události|Odesílá se, když modul je poprvé vytvořena.|  
|Vstupní bod události|Odesílá se, když má laděný program spustit jeho inicializační kód a dosáhla své první vstupní bod uživatele.|  
|Události výjimky|Odesílá se, když spuštěný program narazí na výjimku.|  
|Události dokončení vyhodnocení výrazů|Odeslány po dokončení asynchronní výraz hodnocení.|  
|Najít Symbol události|Posílá vždycky, když je DE je potřeba požádat uživatele o nalezení symbolů pro modul.|  
|Načíst události dokončení|Odesílány pouze po dokončení úvodního programového zatížení a první kód je spuštěn v programu.|  
|Zpráva události|Odesílá se, když se uživatelům pošlou zprávy.|  
|Události načtení modulu|Odesílá se, když je nový modul načten nebo byla uvolněna.|  
|Výstupní řetězec události|Odesílá se, když program zapíše výstup ladění.|  
|Vytváření a ničení událostí|Odesílat oznámení vytvoření nebo zničení procesy, programy, vlastnosti, relace a vlákna, integrovaném vývojovém prostředí sady Visual Studio můžete udržovat přehled o stavu programy, který se právě ladí.|  
|Krok dokončení události|Odesílá se, když krok je dokončen.|  
|Události změny názvu vlákna|Odesílá se, když uživatel změní název vlákna.|  
|Události změny název programu|Odesílá se, když uživatel změní název programu.|  
  
## <a name="see-also"></a>Viz také  
 [Odesílání událostí](../../extensibility/debugger/sending-events.md)
