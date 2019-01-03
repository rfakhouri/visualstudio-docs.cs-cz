---
title: Ověře grafiky | Dokumentace Microsoftu
ms.date: 03/02/2017
ms.topic: conceptual
f1_keywords:
- vs.graphics.FrameValidation
ms.assetid: 1e639182-1301-4e28-9c1e-b5df732f3f1b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2add8032a1fa5da983c66ab5cfabede78f4c65c8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891771"
---
# <a name="graphics-frame-validation"></a>Ověření snímku grafiky
<!-- VERSIONLESS --> Visual Studio 2017 a větší podporu **ověření snímku** nástroj.  V okně rámce ověření se zobrazí chyby a upozornění související s seznamu událostí.  Chcete-li zobrazit toto okno, vyberte **zobrazení > ověření snímku** nabídky.

![Ověření snímku](media/gfx_diag_frame_validation.png)

Klikněte na tlačítko **spustit ověření** tlačítko v levém horním rohu k zahájení analýzy.  Může trvat několik minut v závislosti na složitosti rámce.  Data, která se zobrazí zde se kombinace ze dvou zdrojů: zprávy této D3D samotné vysílá při [vrstev SDK](/windows/desktop/direct3d11/overviews-direct3d-11-devices-layers) je povolená a data, která se shromažďují z nástroje pro vlastní vnitřní stav sledování. Jakmile budete hotovi, uvidíte několik sloupců dat:


| **Sloupec** | **Popis** |
|------------| - |
| Id události | ID, který mapuje na položky v [seznam událostí](graphics-event-list.md) okna. |
| Severity | Poškození, chyby, upozornění, informace o nebo zprávy. |
| Kategorie | Aplikace definované, různé, inicializace, čištění, kompilace, vytvoření stavu, nastavení stavu, získávání stavu, spuštění, zpracování prostředků, shaderů, nadbytečné a nepoužívané. |
| Zpráva | Zpráva přidružená k události. |
| Událost | Událost přidružená k chybě nebo upozornění. |

## <a name="see-also"></a>Viz také  
[Diagnostika grafiky (ladění grafiky DirectX)](visual-studio-graphics-diagnostics.md)   
<!-- /VERSIONLESS -->