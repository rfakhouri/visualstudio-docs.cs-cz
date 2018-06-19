---
title: Proces hostování (vshost.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- vshost.exe
- hosting process
ms.assetid: c6b9e2be-f18d-4d75-ac52-56d55784734b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bba0463870f4d615e45d8f2c11071bfd8a1b8009
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31941948"
---
# <a name="hosting-process-vshostexe"></a>Proces hostování (vshost.exe)

Proces hostování je funkce v sadě Visual Studio, který zlepšuje ladění, povolí ladění na částečné důvěryhodnosti a umožňuje vyhodnocení výrazu doby návrhu. Hostitelský proces soubory obsahují *vshost* v souboru název a jsou umístěny v zadané výstupní složce projektu. Další informace najdete v tématu [ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md).

> [!NOTE]
> Hostování zpracovat soubory (*. vshost.exe*) je pro použití v sadě Visual Studio a nesmí být spustit přímo nebo nasazení s vaší aplikací.

## <a name="improved-debugging-performance"></a>Vylepšení ladění výkonu
 Proces hostování domény aplikace vytvoří a přidruží ladicího programu s aplikací. Provádění těchto úkolů můžou vést významnému zpoždění mezi ladění v době spuštění a čas aplikace zahájí spuštění. Proces hostování pomáhá zvýšit výkon pomocí vytváření domény aplikace a přidružení v ladicím programu na pozadí a ukládání domény aplikace a stav ladicí program mezi spustí aplikace. Další informace o aplikační domény najdete v tématu [aplikační domény](/dotnet/framework/app-domains/application-domains).

## <a name="partial-trust-debugging"></a>Ladění částečné důvěryhodnosti
 Aplikaci lze zadat jako aplikace s částečnou důvěryhodností v [stránka zabezpečení](../ide/reference/security-page-project-designer.md) z **Návrhář projektu**. Ladění aplikace s částečnou důvěryhodností vyžaduje speciální inicializace domény aplikace. Proces hostování používá tento inicializace.

## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu při návrhu
 Vyhodnocení výrazu při návrhu můžete k testování kódu z **Immediate** okno bez nutnosti spuštění aplikace. Proces hostování tento kód provede při vyhodnocení výrazu doby návrhu. Další informace najdete v tématu [hodnot proměnných](../ide/reference/immediate-window.md).

## <a name="see-also"></a>Viz také

- [Ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md)
- [Postupy: zákaz procesu hostování](../ide/how-to-disable-the-hosting-process.md)
- [Příkazové podokno](../ide/reference/immediate-window.md)
- [Aplikační domény](/dotnet/framework/app-domains/application-domains)