---
title: Vytvoření vlastního ladicího stroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, implementing
- debug engines, custom
- debugging [Debugging SDK], custom debug engines
ms.assetid: 52794238-6fae-451c-bf1c-99f344c6f173
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 67a58ab1bf508ba1b2edc7117412638de6c2231a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099543"
---
# <a name="create-a-custom-debug-engine"></a>Vytvoření vlastního ladicího stroje
Ladicí stroj (DE) je komponenta, která umožňuje ladění konkrétní za běhu architektury. Obvykle existuje pouze jedna implementace DE pro každé prostředí za běhu.

> [!NOTE]
>  I když existují samostatné implementace DE pro příkazů jazyka Transact-SQL a JScript, sdílet jeden DE VBScript a JScript.

 Zavedenými spolupracuje s překladač nebo operace systému k poskytování těchto služeb ladění jako ovládací prvek, zarážky a výraz zkušební spuštění. Tyto služby jsou implementované pomocí rozhraní DE a může způsobit, že ladicí program pro přechod mezi různé provozní režimy. Další informace najdete v tématu [provozní režimy](../../extensibility/debugger/operational-modes.md).

 Vytváří se Zavedenými se skládá z následujících kroků:

1. Zaregistrujte Zavedenými pomocí sady Visual Studio

2. Povolit program k ladění

3. Implementace ovládacího prvku a stav zkušební spuštění

4. Odesílání událostí

5. Nastavit ukončení a odpojení

## <a name="in-this-section"></a>V tomto oddílu
 [Registrace vlastního ladicího stroje](../../extensibility/debugger/registering-a-custom-debug-engine.md) vysvětluje kroky potřebné k registraci ladicího stroje pomocí sady Visual Studio, takže je možné.

 [Povolit program k ladění](../../extensibility/debugger/enabling-a-program-to-be-debugged.md) vysvětluje, že před vaše DE můžete ladit program, musíte nejprve spusťte DE nebo připojit k existující program.

 [Implementace ovládacího prvku a stav vyhodnocení provádění](../../extensibility/debugger/execution-control-and-state-evaluation.md) popisuje, proč ladění aplikace vyžaduje implementaci funkce řízení provádění.

 [Odesílání událostí](../../extensibility/debugger/sending-events.md) popisuje komunikaci mezi ladicího programu a DE jako model událostí založené na modelu DCOM.

 [Nastavit ukončení a odpojení](../../extensibility/debugger/termination-and-detaching.md) vysvětluje, jak dosáhnout normální ukončení, což znamená, že neexistují žádné zarážky, výjimky, chyby za běhu nebo nekonečné smyčky v aplikaci k ladění.

 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md) doklady pořadí volání události, k nimž došlo v relaci ladění.

 [Postupy: Ladění vlastního ladicího stroje](../../extensibility/debugger/how-to-debug-a-custom-debug-engine.md) vysvětluje, jak ladit vlastní DE.

## <a name="see-also"></a>Viz také:
- [Rozšiřitelnost ladicího programu Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)