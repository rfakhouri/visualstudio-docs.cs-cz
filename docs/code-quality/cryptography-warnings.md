---
title: "Kryptografie upozornění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5270a9b2cb2801d80dc9a087821e73d6c54bfe1c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cryptography-warnings"></a>Kryptografie upozornění
Upozornění kryptografie podporují bezpečnější knihovny a aplikace prostřednictvím správné použití šifrování. Tato upozornění pomáhají zabránit chybám zabezpečení v programu. Pokud některá z těchto upozornění zakážete, měli byste v kódu jasně označit důvod a také informovat bezpečnostního úředníka vývoje projektu.  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA5350: Nepoužívejte slabé kryptografické algoritmy](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Slabé šifrování algoritmy hash funkce pro používají a dnes z mnoha důvodů, ale nesmí být používají k zajištění důvěrnosti nebo integritu dat, které chrání.        Toto pravidlo aktivuje, pokud najde algoritmy šifrování TripleDES, SHA1 nebo RIPEMD160 v kódu.|  
|[CA5351: Nepoužívejte poškozené kryptografické algoritmy](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Kryptografické algoritmy nejsou považované za bezpečné a jejich použití by měla být důrazně nedoporučuje. Toto pravidlo aktivuje, pokud najde algoritmus hash MD5 nebo DES nebo RC2 šifrovací algoritmy v kódu.|