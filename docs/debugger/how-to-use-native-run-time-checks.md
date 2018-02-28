---
title: "Postupy: použití nativních kontrol za běhu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a36edb5901f8ab67360e276f6a8ff5a2a8d51530
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-native-run-time-checks"></a>Postupy: Použití nativních kontrol za běhu
V jazyce Visual C++, můžete použít nativní [runtime_checks –](/cpp/preprocessor/runtime-checks) k zachycení běžné chyby, jako:  
  
-   Poškození ukazatele zásobníku.  
  
-   Přetečení místní polí.  
  
-   Poškození zásobníku.  
  
-   Závislostí na neinicializovaných místních proměnných.  
  
-   Ke ztrátě dat na přiřazení kratší proměnné.  
  
 Pokud používáte **/RTC** s optimalizované (**/O**) sestavení, výsledků chyby kompilátoru. Pokud používáte `runtime_checks` – Direktiva pragma v optimalizovaného sestavení, – Direktiva pragma nemá žádný vliv.  
  
 Při ladění programu, který má povolené kontroly runtime, je výchozí akce pro program, který chcete zastavit a rozdělit na ladicí program, když dojde k chybě spuštění. Můžete změnit toto výchozí chování pro každé spuštění kontroly. Další informace najdete v tématu [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md).  
  
 Následující postupy popisují postup povolení nativních kontrol za běhu v sestavení ladicí verze a chcete upravit chování nativní kontroly runtime.  
  
 Další témata v této části obsahují informace:  
  
-   [Přizpůsobení Run-Time kontroluje s běhové knihovny jazyka C](../debugger/native-run-time-checks-customization.md)  
  
-   [Run-Time zkontroluje bez běhové knihovny jazyka C](../debugger/using-run-time-checks-without-the-c-run-time-library.md)  
  
### <a name="to-enable-native-run-time-checks-in-a-debug-build"></a>Chcete-li povolit nativních kontrol za běhu v sestavení ladicí verze  
  
-   Použití **/RTC** možnost a propojení s verzí ladicí běhové knihovny jazyka C (/ MDd, např.).  
  
### <a name="to-modify-native-run-time-check-behavior"></a>Chcete-li upravit chování nativní kontroly runtime  
  
-   Použití `runtime_checks` – Direktiva pragma.  
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)   
 [runtime_checks –](/cpp/preprocessor/runtime-checks)   
 [Kontrola chyb za běhu](/cpp/c-runtime-library/run-time-error-checking)