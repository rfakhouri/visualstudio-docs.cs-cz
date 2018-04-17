---
title: Grafika rámce ověření | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.FrameValidation
ms.assetid: 1e639182-1301-4e28-9c1e-b5df732f3f1b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3773fc5df0df05d3f275d7e628bef0def6290d3f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="graphics-frame-validation"></a>Grafika rámce ověření
<!-- VERSIONLESS -->
Visual Studio 2017 a větší podporu **rámce ověření** nástroj.  V okně rámce ověření se zobrazí chyby a upozornění, které jsou přidružené k seznamu těchto událostí.  Chcete-li zobrazit toto okno, vyberte **zobrazení > rámce ověření** nabídky.

![Rámce ověření](media/gfx_diag_frame_validation.png)

Klikněte **spusťte ověření** tlačítko v levém horním rohu zahájíte analýzu.  To může trvat několik minut v závislosti na složitosti rámečku.  Data, která se zobrazí tady je kombinací ze dvou zdrojů: zprávy této D3D samotné vysílá při [SDK vrstvy](https://msdn.microsoft.com/library/windows/desktop/ff476881(v=vs.85).aspx) je povolená a data, která se shromažďují ze stavu interní nástroj pro vlastní sledování. Po dokončení se zobrazí několik sloupce dat:

**Sloupec**|**Popis**
---|---
Id události | ID, která se mapuje na položku v [seznam událostí](graphics-event-list.md) okno.
Závažnost | Poškození, chyby, upozornění, informace o nebo zprávy.
Kategorie | Aplikace definované, různé, inicializace, čištění, kompilace, stavu vytvoření, nastavení stavu, získávání stavu, provádění, zpracování prostředků, shaderu redundantní a nepoužívané.
Zpráva | Zpráva přidružená k události.
Událost | Událost související s chyby nebo upozornění.

## <a name="see-also"></a>Viz také  
[Diagnostika grafiky (ladění grafiky DirectX)](visual-studio-graphics-diagnostics.md)   
<!-- /VERSIONLESS -->