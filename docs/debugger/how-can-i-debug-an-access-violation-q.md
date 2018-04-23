---
title: Jak mohu ladit narušení přístupu C++? | Microsoft Docs
ms.custom: ''
ms.date: 05/23/2017
ms.technology: vs-ide-debug
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
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: b131ba4acf761a11aa9f39807d1db3202b021c9d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-can-i-debug-a-c-access-violation"></a>Jak mohu ladit narušení přístupu C++?
## <a name="problem-description"></a>Popis problému  
 Moje program vytvoří porušení přístupu. Jak můžete ladit to?  
  
## <a name="solution"></a>Řešení  
 Pokud dojde k narušení přístupu na řádek kódu, který dereferences více ukazatele, může být obtížné zjistit, které ukazatel způsobila porušení přístupu. Od verze Visual Studio 2015 Update 1, dialogové okno výjimku teď explicitně názvy ukazatele, která způsobila porušení přístupu.  
  
 Například zadány následující kód, měli byste obdržet porušení přístupu:  
  
```C++  
#include <iostream>  
using namespace std;  
  
class ClassB {  
public:  
        ClassC* C;  
        ClassB() {  
                C = new ClassC();  
        }  
     void printHello() {  
                cout << "hello world";  
        }  
};  
  
class ClassA {  
public:  
    ClassB* B;  
      ClassA() {  
                B = nullptr;  
        }  
};  
  
int main() {  
    ClassA* A = new ClassA();  
      A->B->printHello();  
}  
```  
  
 Pokud spustíte tento kód ve Visual Studiu 2015 Update 1, byste měli vidět následující dialogové okno výjimka:  
  
 ![AccessViolationCPlus](../debugger/media/accessviolationcplus.png "AccessViolationCPlus")  
  
 Pokud nemůže zjistit, proč má ukazatel způsobila narušení přístupu, sledování prostřednictvím kódu a ujistěte se, že příčinou problému ukazatele přiřazený správně.  Je-li předán jako parametr, ujistěte se, že je předán správně a nejsou omylem vytváření [Nedávná kopie](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy). Pak ověřte, že hodnoty se neměnily neúmyslně někde v programu vytvořením zarážku dat pro ukazatele dotyčném a ujistěte se, že se se nemění jinde v programu. Další informace o zarážkách data, najdete v části data zarážek v [pomocí zarážek](../debugger/using-breakpoints.md).  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)