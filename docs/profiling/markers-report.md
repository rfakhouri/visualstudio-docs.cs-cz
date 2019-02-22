---
title: Sestava značek | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.markers
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 765fd6db153f30ad312ea873919a20e5f885b158
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613879"
---
# <a name="markers-report"></a>Sestava značek
Značky sestava obsahuje seznam značek v zobrazený časový rámec.  Posouvání nebo změna měřítka zobrazení nebo skrytí procesu, může způsobit, že značky se zobrazí nebo zmizí. Sestava obsahuje informace o jednotlivých značky:

- Čas, kdy je relativní vzhledem k začátku trasování začal.

- Vlastnost duration. Doba trvání je nula, příznaky a zprávy, protože představují okamžiku.

- ID podprocesu, který provedl vygenerování.

- Zprostředkovatel událostí sledování pro Windows (ETW), který provedl vygenerování.

- Řada značky, odkud byla zapsána.

- Kategorie události, které patří.

- Jeho úroveň důležitosti.

- Jeho typ (značka span, příznak nebo zprávy).

- Podrobný popis co představuje

  Zvolte **exportovat** tlačítko pro uložení sestavy značky jako soubor CSV. Data můžete použít v souboru CSV s jinými aplikacemi nebo nástroje.

> [!NOTE]
>  Sestava značek můžete zobrazit značky 1 000. Pokud chcete zobrazit všechny značky, exportujte do souboru CSV úplnou sestavu.