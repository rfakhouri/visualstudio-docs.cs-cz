---
title: Karta Obecné, dialogové okno vlastností procesů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: 86f4d61d-a594-4aac-8960-c5279b4a10fd
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9256ca4141e9e4ec9e5ae218f1e5a11bf2fa5362
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182284"
---
# <a name="general-tab-process-properties-dialog-box"></a>Karta Obecné, dialogové okno vlastností procesu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Použití **Obecné** karta Další informace o konkrétní proces. Pro zobrazení [dialogové okno vlastností procesu](../debugger/process-properties-dialog-box.md), přesunout fokus [zobrazení procesů](../debugger/processes-view.md) okno. Vyberte libovolný uzel procesu ve stromové struktuře a pak zvolte **vlastnosti** z **zobrazení** nabídky.  
  
 Následující nastavení jsou k dispozici na **Obecné** kartu:  
  
|Entry|Popis|  
|-----------|-----------------|  
|**Název modulu**|Název modulu.|  
|**ID procesu**|Jedinečný Identifikátor tohoto procesu. Čísla ID procesu jsou opakovaně využívána, takže identifikují proces pouze po dobu životnosti procesu. Typ objektu procesu se vytvoří při spuštění programu. Všechna vlákna v procesu sdílet stejnou adresní prostor a mají přístup ke stejným datům.|  
|**Základní priorita**|Aktuální základní priorita tohoto procesu. Vlákna v rámci procesu můžete zvýšit a snížit své vlastní základní priorita relativní k základní priorita procesu.|  
|**Vlákna**|Počet vláken, které jsou aktuálně aktivní v tomto procesu.|  
|**Čas procesoru**|Celkový Procesorový čas strávený na tento proces a jeho vlákna. Rovno uživatelský čas plus privilegovaného času.|  
|**Čas uživatele**|Kumulativní uplynulý čas, který tento proces vláken mít stráví prováděním kódu v uživatelském režimu v jiných než nečinných vláken. Aplikace jsou spouštěny v uživatelském režimu, stejně jako podsystémy, jako je například Správce oken a stroj grafiky.|  
|**Privilegovaného času**|Celkový uplynulý čas tento proces běžel v privilegovaném režimu v jiných než nečinných vláken. Vrstva služby, rutin výkonný a jádro spustit v privilegovaném režimu. Ovladače zařízení u většiny zařízení než grafických adaptérů a tiskárny také spustit v privilegovaném režimu. Nějakou práci, která provádí Windows pro vaši aplikaci může objevit v jiných procesech subsystému kromě privilegovaného času.|  
|**Uplynulý čas**|Celkový uplynulý čas, který tento proces běžel.|
