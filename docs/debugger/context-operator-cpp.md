---
title: Operátor kontextu v ladicím programu (C++) | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: 9222a36bd1e03a1f213a0d3ea0e86e269e912d12
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53889576"
---
# <a name="context-operator-in-the-visual-studio-debugger-c"></a>Operátor kontextu v ladicím programu sady Visual Studio (C++)
Operátor kontextu v jazyce C++ můžete použít k určení umístění zarážky, název proměnné nebo výrazu. Operátor kontextu je vhodné při zadání názvu z vnějšího oboru, který je jinak skrytý místní název.  
  
##  <a name="BKMK_Using_context_operators_to_specify_a_symbol"></a> Syntaxe  
 Existují dva způsoby určení kontextu:  
  
1.  {, [*modulu*]} *výraz*  
  
     Složené závorky musí obsahovat dvě čárky a modulu (spustitelné nebo knihovna DLL) název nebo úplnou cestu.  
  
     Například, chcete-li nastavit zarážku na `SomeFunction` funkce EXAMPLE.dll:  
  
    ```C++  
    {,,EXAMPLE.dll}SomeFunction  
    ```  
  
2.  *modul*! *výraz*  
  
    ```C++  
    EXAMPLE.dll!SomeFunction  
    ```  
  
- *modul* je název modulu. Můžete použít úplnou cestu k rozlišení mezi moduly se stejným názvem.  
  
   Pokud *modulu* cesta obsahuje čárku, vložené místo nebo složené závorky, je nutné použít cesty v uvozovkách, tak, aby analyzátor kontextu správně rozpozná řetězec. Jednoduché uvozovky jsou považovány za součást názvu souboru Windows, je nutné použít dvojitých uvozovek. Například  
  
  ```C++  
  {,,"a long, long, library name.dll"} g_Var  
  ```  
  
- *výraz* je libovolný platný výraz jazyka C++, který se přeloží na platný cíl, například název funkce, název proměnné nebo adresa ukazatele v *modulu*.  
  
  Chyba při vyhodnocování výrazu narazí na symbol ve výrazu, prohledá pro symbol v tomto pořadí:  
  
1.  V rámci oboru lexikální směrem ven, počínaje aktuální blok řadu příkazů uzavřeny ve složených závorkách a ven pokračujte v nadřízeném bloku. Aktuální blok je kód, který obsahuje aktuální umístění, adresa ukazatele instrukce.  
  
2.  Rozsah funkce. Aktuální funkce.  
  
3.  Pokud je aktuální umístění uvnitř členské funkce C++ oboru třídy. Rozsah třídy obsahuje všechny základní třídy. Chyba při vyhodnocování výrazu používá pravidla dominance v normální.  
  
4.  Globální symboly v aktuálním modulu.  
  
5.  Veřejné symboly v aktuálním programu.