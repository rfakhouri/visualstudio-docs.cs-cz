---
title: Kontextový operátor (C++) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.operators
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- expressions [C++], native debugger
- evaluation
- format specifiers, expressions
- context operator, in expressions
- debugging [C++], expressions
- native expression evaluator
ms.assetid: 73cc9afe-f4a4-474e-bb89-5a33fb5e570c
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8a3c033175b1ee7fcd0d7fcbaeae5d64a928289
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682064"
---
# <a name="context-operator-c"></a>Kontextový operátor (C++)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kontextu – operátor (C++)](https://docs.microsoft.com/visualstudio/debugger/context-operator-cpp).  
  
Operátor kontextu v jazyce C++ můžete použít k určení umístění zarážky, název proměnné nebo výrazu. Operátor kontextu je vhodné při zadání názvu z vnějšího oboru, který je jinak skrytý místní název.  
  
##  <a name="BKMK_Using_context_operators_to_specify_a_symbol"></a> Syntaxe  
 Existují dva způsoby určení kontextu:  
  
1.  {, [*modulu*]} *výraz*  
  
     Složené závorky musí obsahovat dvě čárky a modulu (spustitelné nebo knihovna DLL) název nebo úplnou cestu.  
  
     Například, chcete-li nastavit zarážku na `SomeFunction` funkce EXAMPLE.dll:  
  
    ```cpp  
    {,,EXAMPLE.dll}SomeFunction  
    ```  
  
2.  *modul*! *výraz*  
  
    ```cpp  
    EXAMPLE.dll!SomeFunction  
    ```  
  
-   *modul* je název modulu. Můžete použít úplnou cestu k rozlišení mezi moduly se stejným názvem.  
  
     Pokud *modulu* cesta obsahuje čárku, vložené místo nebo složené závorky, je nutné použít cesty v uvozovkách, tak, aby analyzátor kontextu správně rozpozná řetězec. Jednoduché uvozovky jsou považovány za součást názvu souboru Windows, je nutné použít dvojitých uvozovek. Například  
  
    ```cpp  
    {,,"a long, long, library name.dll"} g_Var  
    ```  
  
-   *výraz* je libovolný platný výraz jazyka C++, který se přeloží na platný cíl, například název funkce, název proměnné nebo adresa ukazatele v *modulu*.  
  
 Chyba při vyhodnocování výrazu narazí na symbol ve výrazu, prohledá pro symbol v tomto pořadí:  
  
1.  V rámci oboru lexikální směrem ven, počínaje aktuální blok řadu příkazů uzavřeny ve složených závorkách a ven pokračujte v nadřízeném bloku. Aktuální blok je kód, který obsahuje aktuální umístění, adresa ukazatele instrukce.  
  
2.  Rozsah funkce. Aktuální funkce.  
  
3.  Pokud je aktuální umístění uvnitř členské funkce C++ oboru třídy. Rozsah třídy obsahuje všechny základní třídy. Chyba při vyhodnocování výrazu používá pravidla dominance v normální.  
  
4.  Globální symboly v aktuálním modulu.  
  
5.  Veřejné symboly v aktuálním programu.





