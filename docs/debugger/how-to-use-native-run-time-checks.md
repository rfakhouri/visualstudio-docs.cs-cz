---
title: 'Postupy: Použití nativních kontrol za běhu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- c.runtime.errorchecks
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- /RTC compiler option [C++], /O compiler option
- run-time checks, native
- stack, pointer corruption
- stack pointers, corruption
- /O compiler option, /RTC option
- run-time errors, error checks
- O compiler option, /RTC option
- debugger, runtime errors
- variables [debugger], loss of data
- runtime_checks pragma
- variables [debugger], catching dependencies on uninitialized local variables
- run-time errors, debugging
- debugger, native run-time checks
- optimized build option
- RTC compiler option, /O compiler option
- native run-time checks
- run-time checks
- debugging arrays
- stack pointers
- arrays [Visual Studio], debugging
ms.assetid: dc7b2f1e-5ff6-42e0-89b3-dc9dead83ee1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 4ccf0fea80ddfcc7db0921512391f5063a8f2dad
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62846967"
---
# <a name="how-to-use-native-run-time-checks"></a>Postupy: Použití nativních kontrol za běhu
Ve Vizuálu C++, můžete použít nativní [runtime_checks –](/cpp/preprocessor/runtime-checks) zachytit běžné chyby za běhu, jako:

- Poškození ukazatele zásobníku.

- Přetečení místního pole.

- Poškození zásobníku.

- Závislostí na neinicializovaných místních proměnných.

- Ztráta dat na přiřazení k proměnné kratší.

  Pokud používáte **/RTC** s optimalizované (**/O**) výsledky Chyba kompilátoru sestavení. Pokud používáte `runtime_checks` direktivy pragma v optimalizovaných sestavení, direktivy pragma nemá žádný vliv.

  Když ladíte program, který má povolené kontroly za běhu, je výchozí akce pro program a řízení ladicímu programu, když dojde k chybě za běhu. Můžete změnit toto výchozí chování pro všechny kontroly za běhu. Další informace najdete v tématu [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md).

  Následující postupy popisují, jak povolit nativní kontroly za běhu v sestavení pro ladění a jak změnit chování nativní kontroly za běhu.

  Další témata v této části obsahují informace:

- [Přizpůsobení Run-Time zkontroluje knihovny Run-Time jazyka C](../debugger/native-run-time-checks-customization.md)

- [Pomocí za běhu bez běhové knihovny jazyka C kontrol](../debugger/using-run-time-checks-without-the-c-run-time-library.md)

### <a name="to-enable-native-run-time-checks-in-a-debug-build"></a>K povolení nativních kontrol za běhu v sestavení pro ladění

- Použití **/RTC** možnost a propojení s ladicí verzí knihovny run-time jazyka C (/ MDd, například).

### <a name="to-modify-native-run-time-check-behavior"></a>Jestliže chcete upravit chování nativní kontroly za běhu

- Použití `runtime_checks` direktivy pragma.

## <a name="see-also"></a>Viz také
- [Ladění v sadě Visual Studio](../debugger/index.md)
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)
- [runtime_checks](/cpp/preprocessor/runtime-checks)
- [Kontrola chyb za běhu](/cpp/c-runtime-library/run-time-error-checking)