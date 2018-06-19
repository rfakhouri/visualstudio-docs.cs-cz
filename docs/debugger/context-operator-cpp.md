---
title: Context – operátor v ladicím programu (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.operators
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- expressions [C++], native debugger
- evaluation
- format specifiers, expressions
- context operator, in expressions
- debugging [C++], expressions
- native expression evaluator
ms.assetid: 73cc9afe-f4a4-474e-bb89-5a33fb5e570c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 4640739f72046e1c223229bfc33ba34dcafb520f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466042"
---
# <a name="context-operator-in-the-visual-studio-debugger-c"></a>Context – operátor v ladicím programu sady Visual Studio (C++)
Operátor kontextu můžete v jazyce C++ pro kvalifikaci zarážek umístění, název proměnné nebo výraz. Operátor kontextu je užitečné pro určení názvu z vnějšího oboru, jinak skrytá pomocí místní název.  
  
##  <a name="BKMK_Using_context_operators_to_specify_a_symbol"></a> Syntaxe  
 Zadávání kontextu dvěma způsoby:  
  
1.  {,, [*modulu*]} *výraz*  
  
     Složené závorky musí obsahovat dvě čárky a modulu (spustitelného souboru nebo knihovny DLL) název nebo úplnou cestu.  
  
     Chcete-li například nastavit zarážky v `SomeFunction` funkce EXAMPLE.dll:  
  
    ```C++  
    {,,EXAMPLE.dll}SomeFunction  
    ```  
  
2.  *modul*! *výraz*  
  
    ```C++  
    EXAMPLE.dll!SomeFunction  
    ```  
  
-   *modul* je název modulu. Úplná cesta můžete použít k rozlišení mezi modulů se stejným názvem.  
  
     Pokud *modulu* cesta obsahuje čárkami, vložené místo nebo složená závorka, je nutné použít cesty do uvozovek tak, aby analyzátor kontextu správně rozpoznat řetězec. Jednoduché uvozovky jsou považovány za součást názvu souboru systému Windows, je nutné použít uvozovky. Například  
  
    ```C++  
    {,,"a long, long, library name.dll"} g_Var  
    ```  
  
-   *výraz* je libovolný platný výraz C++, který se přeloží na platný cíl, například název funkce, název proměnné nebo adresu ukazatele v *modulu*.  
  
 Při vyhodnocování výrazu zaznamená symbol ve výrazu, hledá symbol v následujícím pořadí:  
  
1.  Lexikální rozsah směrem ven, počínaje aktuálnímu bloku, řadu příkazů uzavřené do složených závorek a budete pokračovat i vnějšího bloku. Aktuální blok je kódu, který obsahuje aktuální umístění, adresa instrukce ukazatele.  
  
2.  Rozsah funkce. Funkci current.  
  
3.  Rozsah třídy, pokud je aktuální umístění uvnitř C++ členské funkce. Rozsah třídy zahrnuje všechny základní třídy. Vyhodnocovací filtr výrazů používá normální dominance pravidla.  
  
4.  Globální symboly v aktuální modul.  
  
5.  Veřejné symboly v aktuálním programem.