---
title: Upozornění kryptografie | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c573d461b477bbcdc7e988ea66f03d5a7cc0fdb6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201451"
---
# <a name="cryptography-warnings"></a>Upozornění kryptografie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Upozornění kryptografie podporují bezpečnější knihovny a aplikací prostřednictvím správné použití šifrování. Tato upozornění pomáhají zabránit chybám zabezpečení v programu. Pokud některá z těchto upozornění zakážete, měli byste v kódu jasně označit důvod a také informovat bezpečnostního úředníka vývoje projektu.  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA5350: Nepoužívejte slabé kryptografické algoritmy](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Algoritmy slabé šifrování a hashovací funkce se dnes používají pro z několika důvodů, ale by neměly být používají zajistit důvěryhodnost nebo integritu dat, která chrání.        Toto pravidlo aktivuje, když zjistí, TripleDES, SHA1 nebo RIPEMD160 algoritmy v kódu.|  
|[CA5351: Nepoužívejte poškozené kryptografické algoritmy](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Kryptografické algoritmy nejsou považované za bezpečné a jejich použití by mělo být vás od toho důrazně odrazujeme. Toto pravidlo aktivuje, když najde algoritmus hash MD5 nebo DES nebo RC2 šifrovací algoritmy v kódu.|
