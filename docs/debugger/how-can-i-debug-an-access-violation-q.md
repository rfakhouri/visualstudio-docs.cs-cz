---
title: Ladění narušení přístupu jazyka C++ | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 02/05/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 9311d754-0ce9-4145-b147-88b6ca77ba63
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 9ceb160c93e79d43428685d7b0e82a8a0670cc01
ms.sourcegitcommit: 5dc74b4fdff1357df43a19f6e8a51d7bf706abd6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2019
ms.locfileid: "55767799"
---
# <a name="how-can-i-debug-a-c-access-violation"></a>Jak mohu ladit porušení přístupu jazyka C++?

## <a name="problem-description"></a>Popis problému

Tento program vytvoří narušení přístupu. Jak to lze odladit?  
  
## <a name="solution"></a>Řešení

Pokud dojde k narušení přístupu na řádek kódu, který přistoupí přes většího počtu ukazatelů, může být obtížné zjistit, které ukazatel způsobil narušení přístupu. Od verze Visual Studio 2015 Update 1, dialogové okno výjimky nyní explicitně názvy ukazatel, který způsobil narušení přístupu.  
  
Například směru následujícím kódem, měli byste získat narušení přístupu:  

```C++
#include <iostream>  
using namespace std;  
  
class ClassC {
public:
  void printHello() {
    cout << "hello world";
  }
};

class ClassB {
public:
  ClassC* C;
  ClassB() {
    C = new ClassC();
  }
};

class ClassA {
public:
  ClassB* B;
  ClassA() {
    // Uncomment to fix
    // B = new ClassB();
  }
};

int main() {
  ClassA* A = new ClassA();
  A->B->C->printHello();

}
```  

Při spuštění tohoto kódu ve Visual Studio 2015 Update 1, byste měli vidět následující dialogové okno výjimky:  
  
![AccessViolationCPlus](../debugger/media/accessviolationcplus.png "AccessViolationCPlus")  
  
Pokud nelze určit, proč je ukazatel způsobil narušení přístupu, trasování skrze kód a ujistěte se, že ukazatel příčinou problému, má přiřazenou správně.  Pokud je předán jako parametr, ujistěte, že je jí předán správně, a nejsou omylem vytváření [Nedávná kopírování](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy). Ověřte, že hodnoty nejsou mění neúmyslně někde v programu vytvořením datové zarážky pro ukazatele dotyčný zajistit, aby že se nemění jinde v programu. Další informace o datové zarážky, najdete v části zarážky data v [pomocí zarážek](../debugger/using-breakpoints.md).  
  
## <a name="see-also"></a>Viz také  
 [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)