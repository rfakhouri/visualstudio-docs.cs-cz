---
title: Nepodporované scénáře v Návrháři postupu provádění ladění | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
caps.latest.revision: 4
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 651777d3488460394b79488d3d0fc67ff286bbfb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677374"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nepodporované scénáře ladění v návrháři postupu provádění
V Návrháři postupu provádění [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] přidali spoustu nových funkcí, ale stále existují některé scénáře ladění, které se nepodporuje. Tento dokument podrobně popisuje nepodporované scénáře ladění návrháře postupu provádění.  
  
-   Provádění nelze pokračovat, až se upravil kód.  
  
-   Spuštění nemůže pokračovat z libovolného bodu v pracovním postupu (nastavit další).  
  
-   Provádění nelze pokračovat, dokud nenastane kurzoru (Spustit ke kurzoru).  
  
-   Chcete-li ladit pracovní postupy vytvořené v kódu bez použití návrháře nelze použít Návrháře postupu provádění.  
  
-   Pracovní postupy vytvořené v dřívějších verzích [!INCLUDE[wf](../includes/wf-md.md)] není možné ladit v [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] návrháře.  
  
-   Zarážky nelze zadat u propojení mezi aktivitami nebo <xref:System.Activities.Statements.Flowchart> uzly.  
  
-   Během ladění není k dispozici do schránky.  
  
-   Zarážky nejsou zachovány při jsou aktivity kopírování a vložení.  
  
-   V okně zásobník volání nelze nastavit zarážky pracovního postupu.  
  
-   Při vytváření zarážky v návrháři **řádku** a **znak** nastavení v **Nová zarážka** nepoužívají dialogového okna.  
  
-   Zarážka okna nebo v místní nabídce nepodporuje následující sloupce nebo možnosti pro ladění pracovního postupu:  
  
    -   Podmínka  
  
    -   Počet přístupů  
  
    -   Při průchodu  
  
    -   Funkce  
  
    -   Data  
  
    -   Proces  
  
    -   Přejít na zpětný překlad