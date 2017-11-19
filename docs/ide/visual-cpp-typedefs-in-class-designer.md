---
title: "Visual C++ definice TypeDef v Návrháři tříd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.typedef
- vs.classdesigner.aliasofline
helpviewer_keywords: Class Designer [Visual Studio], typedefs
ms.assetid: c1984108-71fc-4d3a-b4d4-3eac2c6b4ebf
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d6df83d459165b4814fcac129bc36b64d821efb6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-typedefs-in-class-designer"></a>Definice Typedefs jazyka Visual C++ v návrháři tříd
Příkazy TypeDef vytvořit jednu nebo více vrstev dereference mezi názvem a jeho zdrojovým typem. Návrhář tříd podporuje typy C++ typedef, které jsou deklarovány s klíčovým slovem `typedef`, například:  
  
```  
typedef class coord  
{  
   void P(x,y);  
   unsigned x;  
   unsigned y;  
} COORD;  
```  
  
 Pak můžete tento typ deklarovat instanci:  
  
 `COORD OriginPoint;`  
  
 I když můžou deklarovat typedef bez názvu, návrhář tříd nebude používat název značky, který zadáte; použije název, který generuje zobrazení tříd. Například následující prohlášení, je platný, ale zobrazí se v zobrazení tříd a návrhář tříd jako objekt s názvem **__unnamed**:  
  
```  
typedef class coord  
{  
   void P(x,y);  
   unsigned x;  
   unsigned y;  
};  
```  
  
 Další informace o používání `typedef` zadejte najdete v tématu [typedef specifikátor](https://msdn.microsoft.com/en-us/library/05w82thz.aspx).  
  
 Obrazec typedef C++ má tvar s typem zadaným v typedef. Například, pokud zdroj deklaruje `typedef class`, tvar, který má zaokrouhlené rozích a popisku **třída**. Pro `typedef struct`, tvar, který má hranatými rohy a popisku **struktura**.  
  
 Třídy a struktury může mít vnořené deklarované v rámci jejich; – definice TypeDef třídy a struktury tvary tedy můžete zobrazit vnořené typedef – deklarace jako vnořené tvarů.  
  
 TypeDef obrazce podpory **zobrazit jako přidružení** a **zobrazit jako asociace kolekce** příkazy v místní nabídce.  
  
 Toto jsou některé příklady typdef typy, které podporuje návrhář tříd:  
  
 `typedef type name`  
  
 *název* : *typu*  
  
 – definice typedef  
  
 Vykreslí přidružení propojující zadejte *název*, pokud je to možné.  
  
 `typedef void (*func)(int)`  
  
 `func: void (*)(int)`  
  
 – definice typedef  
  
 TypeDef pro ukazatelů na funkce. Se nevykresluje žádné čáry přidružení.  
  
 Návrhář tříd nezobrazuje definice typu, pokud jeho typ zdroje je ukazatel na funkci.  
  
```  
typedef int MyInt;  
class A {  
   MyInt I;  
};  
```  
  
 `MyInt: int`  
  
 – definice typedef  
  
 `A`  
  
 Třída  
  
 Nakreslí řádku s přidružení odkazující na obrazce typu cílový z obrazce typu zdroje.  
  
 `Class B {};`  
  
 `typedef B MyB;`  
  
 `B`  
  
 Třída  
  
 `MyB : B`  
  
 – definice typedef  
  
 Pravým tlačítkem myši na tvar typedef a kliknutím na **zobrazit jako přidružení** zobrazí typedef nebo třídy a **Alias** řádku připojení dvě tvarů (podobně jako řádku s přidružení).  
  
 `typedef B MyB;`  
  
 `typedef MyB A;`  
  
 `MyBar : Bar`  
  
 – definice typedef  
  
 Stejné jako výše.  
  
```  
Class B {};  
typedef B MyB;  
  
class A {  
   MyB B;  
};  
```  
  
 `B`  
  
 Třída  
  
 `MyB : B`  
  
 – definice typedef  
  
 `A`  
  
 Třída  
  
 `MyB`je vnořené typedef tvar.  
  
 `#include <vector>`  
  
 `...`  
  
 `using namespace std;`  
  
 `...`  
  
 `typedef vector<int> MyIntVect;`  
  
 `vector<T>`– Třída  
  
 `MyIntVect : vector<int>`  
  
 – definice typedef  
  
 `class B {};`  
  
 `typedef B MyB;`  
  
 `class A : MyB {};`  
  
 `MyB : B`  
  
 – definice typedef  
  
 -> B  
  
 `B`  
  
 `A`  
  
 Třída  
  
 -> MyB  
  
 Návrhář tříd nepodporuje zobrazení tento typ vztahu s použitím příkazu nabídky kontextu.  
  
 `#include <vector>`  
  
 `Typedef MyIntVect std::vector<int>;`  
  
 `Class MyVect : MyIntVect {};`  
  
 `std::vector<T>`  
  
 Třída  
  
 `MyIntVect : std::vector<int>`  
  
 – definice typedef  
  
 `MyVect`  
  
 Třída  
  
 -> MyIntVect  
  
## <a name="see-also"></a>Viz také  
 [Práce s kódem jazyka Visual C++ (návrhář tříd)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [TypeDef – specifikátor](https://msdn.microsoft.com/en-us/library/05w82thz.aspx)