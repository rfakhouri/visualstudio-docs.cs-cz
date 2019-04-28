---
title: Ověře grafiky | Dokumentace Microsoftu
ms.date: 03/02/2017
ms.topic: conceptual
f1_keywords:
- vs.graphics.FrameValidation
ms.assetid: 1e639182-1301-4e28-9c1e-b5df732f3f1b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce283e5cbab30b612a02ec447113ad11e206a7f3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62895867"
---
# <a name="graphics-frame-validation"></a>Ověření snímku grafiky
<!-- VERSIONLESS -->
Visual Studio 2017 a větší podporu **ověření snímku** nástroj.  V okně rámce ověření se zobrazí chyby a upozornění související s seznamu událostí.  Chcete-li zobrazit toto okno, vyberte **zobrazení > ověření snímku** nabídky.

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