---
title: "Fragmenty kódu v jazyce Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74e26fd4-e5ca-4611-a816-0a521b4947a0
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d9a34e371797317d3163f8288474e7a902b4f82
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-code-snippets"></a>Fragmenty kódu v jazyce Visual C++
Fragmenty kódu v sadě Visual Studio, můžete použít přidat kód pro běžně používané soubory s kódem jazyka C++. Obecně platí fragmenty kódu můžete používat stejným způsobem jako v C#, ale sadu výchozí fragmenty kódu se liší.  
  
 Můžete přidat fragment kódu v konkrétních místech v kódu (vložení) nebo obklopit některé vybrané kódu pomocí fragmentu kódu.  
  
## <a name="inserting-a-code-snippet"></a>Vkládání fragmentu kódu  
 Pokud chcete vložit fragment kódu, otevřete soubor kódu C++ (sada nebo .h), klikněte na tlačítko někde v souboru a proveďte jednu z následujících akcí:  
  
-   Klikněte pravým tlačítkem a získat v místní nabídce vyberte **Vložit fragment kódu**  
  
-   V **upravit nebo IntelliSense** nabídce vyberte možnost **Vložit fragment kódu**  
  
-   Použití klávesových zkratek: **CTRL + K + X**  
  
 Zobrazí seznam možností počínaje **#if**. Když vyberete **#if**, měli byste vidět následující kód do souboru přidán:  
  
```cpp  
#if 0  
  
#endif // 0  
```  
  
 Pak můžete 0 nahradit správné podmínku.  
  
## <a name="using-a-code-snippet-to-surround-selected-code"></a>Obklopit pomocí fragmentu kódu vybrané kódu  
 Chcete-li obklopit vybraný úsek kódu pomocí fragmentu kódu, vyberte řádek (nebo více řádků) a proveďte jednu z následujících:  
  
1.  Klikněte pravým tlačítkem a získat v místní nabídce vyberte **příkazu Obklopit s**  
  
2.  V **upravit nebo IntelliSense** nabídce vyberte možnost **příkazu Obklopit s**  
  
3.  Použití klávesových zkratek: **CTRL + K + S**  
  
 Vyberte **#if**. Měli byste vidět zhruba takhle:  
  
```cpp  
#if 0  
#include "pch.h"  // or whatever line you had selected  
#endif // 0  
```  
  
 Pak můžete 0 nahradit správné podmínku.  
  
## <a name="where-can-i-find-a-complete-list-of-the-c-code-snippets"></a>Kde úplný seznam fragmenty kódu C++  
 Úplný seznam fragmenty kódu C++ můžete najít na webu **Správce fragmentů kódu** (na **nástroje** nabídky) a nastavení **jazyk** k **Visual C++** . V okně níže, rozbalte položku **Visual C++**. Měli byste vidět názvy všechny fragmenty kódu C++ v abecedním pořadí.  
  
 Názvy většina fragmenty kódu jsou zřejmé, ale některé názvy může být matoucí.  
  
## <a name="class-vs-classi"></a>Třída oproti classi  
 **Třída** fragment obsahuje definice třídy s názvem MyClass, s odpovídající výchozí konstruktor a destruktor, kde se nachází definice konstruktor a destruktor mimo třídy:  
  
```cpp  
class MyClass  
{  
public:  
MyClass();  
~MyClass();  
  
private:  
  
};  
  
MyClass::MyClass()  
{  
}  
  
MyClass::~MyClass()  
{  
}  
```  
  
 Fragment kódu classi také obsahuje definice třídy s názvem MyClass, ale do definice třídy jsou definovány výchozí konstruktor a destruktor:  
  
```cpp  
class MyClass  
{  
public:  
MyClass()  
{  
}  
  
~MyClass()  
{  
}  
  
private:  
  
};  
```  
  
## <a name="for-vs-foreach-vs-forr-vs-rfor"></a>Pro oproti foreach oproti forr vs rfor  
 Existují čtyři různé pro fragmenty kódu, které poskytují různé typy z smyčky for.  
  
 **Pro** fragment obsahuje `for` smyčky, ve kterém je založena na délku (v `size_t`) objektu:  
  
```cpp  
for (size_t i = 0; i < length; i++)  
{  
  
}  
```  
  
 **Foreach** fragment obsahuje `for each` smyčky, který iteruje nad členy kolekce:  
  
```cpp  
for each (object var in collection_to_loop)  
{  
  
}  
```  
  
 **Forr** fragment obsahuje zpětného `for` smyčky, ve kterém je založena na délce objektu (v celých čísel):  
  
```cpp  
for (int i = length - 1; i >= 0; i--)  
{  
  
}  
```  
  
 **Rfor** fragment obsahuje [na základě rozsahu](/cpp/cpp/range-based-for-statement-cpp) pro smyčky (odkaz):  
  
```cpp  
for (auto& i : v)  
{  
  
}  
```  
  
## <a name="the-destructor-snippet-"></a>Fragmentu – destruktor (~)  
 Fragment kódu – destruktor (**~**) ukazuje různé chování v různých kontextech. Pokud je vložit tento fragment kódu uvnitř třídy, poskytuje destruktor pro tuto třídu. Například uděleno následující kód:  
  
```cpp  
class SomeClass {  
  
};  
```  
  
 Pokud vložíte fragmentu destruktor, poskytuje destruktor pro SomeClass:  
  
```cpp  
class SomeClass {  
    ~SomeClass()  
    {  
  
    }  
};  
```  
  
 Pokud se pokusíte vložit fragment – destruktor mimo třídu, poskytuje destruktor s názvem zástupný text:  
  
```cpp  
~TypeNamePlaceholder()  
{  
  
```