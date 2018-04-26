---
title: Fragmenty kódu v jazyce Visual C++
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: 0eca50a938312f6c463ff661c83fd90c9218b5ec
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="visual-c-code-snippets"></a>Fragmenty kódu Visual C++

Fragmenty kódu v sadě Visual Studio, můžete použít přidat kód pro běžně používané soubory s kódem jazyka C++. Obecně platí fragmenty kódu můžete používat stejným způsobem jako v C#, ale sadu výchozí fragmenty kódu se liší.

Můžete přidat fragment kódu v konkrétních místech v kódu (vložení) nebo obklopit některé vybrané kódu pomocí fragmentu kódu.

## <a name="inserting-a-code-snippet"></a>Vkládání fragmentu kódu

Pokud chcete vložit fragment kódu, otevřete soubor kódu C++ (sada nebo .h), klikněte na tlačítko někde v souboru a proveďte jednu z následujících akcí:

- Klikněte pravým tlačítkem a získat v místní nabídce vyberte **Vložit fragment kódu**

- V **upravit nebo IntelliSense** nabídce vyberte možnost **Vložit fragment kódu**

- Použití klávesových zkratek: **Ctrl**+**tisíc**+**X**

Zobrazí seznam možností počínaje **#if**. Když vyberete **#if**, měli byste vidět následující kód do souboru přidán:

```cpp
#if 0

#endif // 0
```

Pak můžete 0 nahradit správné podmínku.

## <a name="using-a-code-snippet-to-surround-selected-code"></a>Obklopit vybraný úsek kódu pomocí fragmentu kódu

Chcete-li obklopit vybraný úsek kódu pomocí fragmentu kódu, vyberte řádek (nebo více řádků) a proveďte jednu z následujících:

- Chcete-li získat v místní nabídce klikněte pravým tlačítkem a vyberte **příkazu Obklopit s**

- Z **upravit** > **IntelliSense** nabídce vyberte možnost **příkazu Obklopit s**

- Použití klávesnice, stiskněte klávesu: **CTRL**+**tisíc**+**S**

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

**Classi** fragment kódu také obsahuje definice třídy s názvem MyClass, ale do definice třídy jsou definovány výchozí konstruktor a destruktor:

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

## <a name="for-vs-forr-vs-rfor"></a>pro oproti forr vs rfor

Existují tři různé **pro** fragmenty kódu, které poskytují různé typy z `for` smyčky.

**Rfor** fragment obsahuje [na základě rozsahu](/cpp/cpp/range-based-for-statement-cpp) pro smyčky (odkaz). Tento konstruktor je upřednostňovaný nad na základě indexu `for` smyčky.

```cpp
for (auto& i : v)
{

}
```

**Pro** fragment obsahuje `for` smyčky, ve kterém je založena na délku (v `size_t`) objektu.

```cpp
for (size_t i = 0; i < length; i++)
{

}
```

**Forr** fragment obsahuje zpětného `for` smyčky, ve kterém je založena na délce objektu (v celá čísla).

```cpp
for (int i = length - 1; i >= 0; i--)
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

## <a name="see-also"></a>Viz také

- [Fragmenty kódu](../ide/code-snippets.md)