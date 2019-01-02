---
title: Upozornění kryptografie
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bff3ffef284c0cbf1503d573ba01c7a88c1c5e95
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53964173"
---
# <a name="cryptography-warnings"></a>Upozornění kryptografie
Upozornění kryptografie podporují bezpečnější knihovny a aplikací prostřednictvím správné použití šifrování. Tato upozornění pomáhají zabránit chybám zabezpečení v programu. Pokud některá z těchto upozornění zakážete, měli byste v kódu jasně označit důvod a také informovat bezpečnostního úředníka vývoje projektu.

|Pravidlo|Popis|
|----------|-----------------|
|[CA5350: Nepoužívejte slabé kryptografické algoritmy](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Algoritmy slabé šifrování a hashovací funkce se dnes používají pro z několika důvodů, ale by neměly být používají zajistit důvěryhodnost nebo integritu dat, která chrání.        Toto pravidlo aktivuje, když zjistí, TripleDES, SHA1 nebo RIPEMD160 algoritmy v kódu.|
|[CA5351: Nepoužívejte poškozené kryptografické algoritmy](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Kryptografické algoritmy nejsou považované za bezpečné a jejich použití by mělo být vás od toho důrazně odrazujeme. Toto pravidlo aktivuje, když najde algoritmus hash MD5 nebo DES nebo RC2 šifrovací algoritmy v kódu.|