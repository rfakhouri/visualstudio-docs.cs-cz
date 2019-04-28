---
title: Definice Typedefs jazyka Visual C++ v návrháři tříd
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.typedef
- vs.classdesigner.aliasofline
helpviewer_keywords:
- Class Designer [Visual Studio], typedefs
ms.assetid: c1984108-71fc-4d3a-b4d4-3eac2c6b4ebf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: ded9e1b6bea0a6f03dd9599b592bba5fba6f91fe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62975117"
---
# <a name="visual-c-typedefs-in-class-designer"></a>Definice typedefs jazyka Visual C++ v Návrháři tříd

[Definice TypeDef](/cpp/cpp/aliases-and-typedefs-cpp#typedefs) příkazy vytvoří jednu nebo více vrstev indirekce mezi názvem a jeho nadřízeného typu. **Návrhář tříd** podporuje typy typedef jazyka C++, které jsou deklarovány pomocí klíčového slova `typedef`, například:

```cpp
typedef class coord
{
   void P(x,y);
   unsigned x;
   unsigned y;
} COORD;
```

Potom můžete tento typ deklarovat instanci:

`COORD OriginPoint;`

## <a name="class-and-struct-shapes"></a>Třídy a struktury obrazce

V **návrhář tříd**, C++ typedef má tvar typu určeného v typedef. Pokud zdroj deklaruje `typedef class`, tvar zaoblené rohy a popisek **třídy**. Pro `typedef struct`, hranaté rohy a popisek má obrazec **struktura**.

Vnořené TypeDef deklarován v nich může mít třídy a struktury. V **návrhář tříd**, třídy a struktury tvary můžete zobrazit vnořené TypeDef – deklarace jako vnořeným obrazcům.

Definice TypeDef obrazce podpory **zobrazit jako přidružení** a **zobrazit jako přidružení kolekce** příkazy v místní nabídce (kontextová nabídka).

### <a name="class-typedef-example"></a>Příklad třídy definice typedef

```cpp
class B {};
typedef B MyB;
```

![Definice typu třídy C++ v Návrháři tříd](media/cpp-class-typedef.png)

### <a name="struct-typedef-example"></a>Příklad struktury – typedef

```cpp
typedef struct mystructtag
{
    int   i;
    double f;
} mystruct;
```

![Typedef – struktura C++ v Návrháři tříd](media/cpp-struct-typedef.png)

## <a name="unnamed-typedefs"></a>Nepojmenovaná definice TypeDef

I když je možné deklarovat definice typu bez názvu, **návrhář tříd** nepoužívá název značky, který zadáte. **Návrhář tříd** používá název, který **zobrazení tříd** generuje. Například následující deklarace je platný, ale zobrazí se v **zobrazení tříd** a **návrhář tříd** jako objekt s názvem **__unnamed**:

```cpp
typedef class coord
{
   void P(x,y);
   unsigned x;
   unsigned y;
};
```

> [!NOTE]
> **Návrhář tříd** – definice TypeDef, jehož typ zdroje je ukazatel na funkci se nezobrazí.

## <a name="see-also"></a>Viz také:

- [Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)
- [Definice TypeDef](/cpp/cpp/aliases-and-typedefs-cpp#typedefs)