---
title: Nepodporované scénáře v Návrháři postupu provádění ladění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
caps.latest.revision: 4
author: steved0x
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7b3b47264190afcc75431a55ad6b8b4512f26ea0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62858188"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nepodporované scénáře ladění v návrháři postupu provádění
V Návrháři postupu provádění [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] přidali spoustu nových funkcí, ale stále existují některé scénáře ladění, které se nepodporuje. Tento dokument podrobně popisuje nepodporované scénáře ladění návrháře postupu provádění.  
  
- Provádění nelze pokračovat, až se upravil kód.  
  
- Spuštění nemůže pokračovat z libovolného bodu v pracovním postupu (nastavit další).  
  
- Provádění nelze pokračovat, dokud nenastane kurzoru (Spustit ke kurzoru).  
  
- Chcete-li ladit pracovní postupy vytvořené v kódu bez použití návrháře nelze použít Návrháře postupu provádění.  
  
- Pracovní postupy vytvořené v dřívějších verzích [!INCLUDE[wf](../includes/wf-md.md)] není možné ladit v [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] návrháře.  
  
- Zarážky nelze zadat u propojení mezi aktivitami nebo <xref:System.Activities.Statements.Flowchart> uzly.  
  
- Během ladění není k dispozici do schránky.  
  
- Zarážky nejsou zachovány při jsou aktivity kopírování a vložení.  
  
- V okně zásobník volání nelze nastavit zarážky pracovního postupu.  
  
- Při vytváření zarážky v návrháři **řádku** a **znak** nastavení v **Nová zarážka** nepoužívají dialogového okna.  
  
- Zarážka okna nebo v místní nabídce nepodporuje následující sloupce nebo možnosti pro ladění pracovního postupu:  
  
    - Podmínka  
  
    - Počet přístupů  
  
    - Při průchodu  
  
    - Funkce  
  
    - Data  
  
    - Proces  
  
    - Přejít na zpětný překlad