---
title: Nepodporované scénáře ladění v návrháři postupu provádění
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 9cda710a3a2f4945e96e706479996da0a1fa7e12
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825734"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nepodporované scénáře ladění v návrháři postupu provádění

Návrháře postupu provádění nepodporuje následující scénáře ladění:

- Provádění nelze pokračovat, až se upravil kód.

- Spuštění nemůže pokračovat z libovolného bodu v pracovním postupu (nastavit další).

- Provádění nelze pokračovat, dokud nenastane kurzoru (Spustit ke kurzoru).

- Chcete-li ladit pracovní postupy vytvořené v kódu bez použití návrháře nelze použít Návrháře postupu provádění.

- Pracovní postupy vytvořené v dřívějších verzích Windows Workflow Foundation (WF) není možné ladit v rozhraní .NET Framework 4 nebo novější.

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
