---
title: Upozornění kryptografie | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 947721de606cb6117ed2fd5f84bbc51e20e08203
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676321"
---
# <a name="cryptography-warnings"></a>Upozornění kryptografie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [upozornění kryptografie](https://docs.microsoft.com/visualstudio/code-quality/cryptography-warnings).  
  
Upozornění kryptografie podporují bezpečnější knihovny a aplikací prostřednictvím správné použití šifrování. Tato upozornění pomáhají zabránit chybám zabezpečení v programu. Pokud některá z těchto upozornění zakážete, měli byste v kódu jasně označit důvod a také informovat bezpečnostního úředníka vývoje projektu.  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA5350: Nepoužívejte slabé kryptografické algoritmy](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Algoritmy slabé šifrování a hashovací funkce se dnes používají pro z několika důvodů, ale by neměly být používají zajistit důvěryhodnost nebo integritu dat, která chrání.        Toto pravidlo aktivuje, když zjistí, TripleDES, SHA1 nebo RIPEMD160 algoritmy v kódu.|  
|[CA5351: Nepoužívejte poškozené kryptografické algoritmy](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Kryptografické algoritmy nejsou považované za bezpečné a jejich použití by mělo být vás od toho důrazně odrazujeme. Toto pravidlo aktivuje, když najde algoritmus hash MD5 nebo DES nebo RC2 šifrovací algoritmy v kódu.|



