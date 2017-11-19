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
ms.openlocfilehash: 4936482aea909938e135e8f61164955dacc9e20b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="cryptography-warnings"></a>Kryptografie upozornění
Upozornění kryptografie podporují bezpečnější knihovny a aplikace prostřednictvím správné použití šifrování. Tato upozornění pomáhají zabránit chybám zabezpečení v programu. Pokud některá z těchto upozornění zakážete, měli byste v kódu jasně označit důvod a také informovat bezpečnostního úředníka vývoje projektu.  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA5350: Nepoužívejte slabé kryptografické algoritmy](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Slabé šifrování algoritmy hash funkce pro používají a dnes z mnoha důvodů, ale nesmí být používají k zajištění důvěrnosti nebo integritu dat, které chrání.        Toto pravidlo aktivuje, pokud najde algoritmy šifrování TripleDES, SHA1 nebo RIPEMD160 v kódu.|  
|[CA5351 Nepoužívejte porušený kryptografické algoritmy](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Kryptografické algoritmy nejsou považované za bezpečné a jejich použití by měla být důrazně nedoporučuje. Toto pravidlo aktivuje, pokud najde algoritmus hash MD5 nebo DES nebo RC2 šifrovací algoritmy v kódu.|