---
title: "Třídy jazyka Visual C++ v Návrháři tříd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.classdesigner.inheritancelinelabel
helpviewer_keywords: Class Designer [Visual Studio], classes
ms.assetid: 75e56f8c-11ef-42a3-b7ec-3d2cf25c581b
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3e6861ba33fed68455fdc6d38aee81549edc516f
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="visual-c-classes-in-class-designer"></a>Třídy jazyka Visual C++ v návrháři tříd
Návrhář tříd podporuje třídy jazyka C++ a vizualizuje nativních tříd jazyka C++ stejným způsobem jako obrazců třídy jazyka Visual Basic a Visual C#, s tím rozdílem, že třídy C++ může mít více vztahů dědičnosti. Můžete rozbalit třída tvar, který má zobrazit další pole a metody ve třídě nebo sbalit, kvůli úspoře místa.  
  
> [!NOTE]
>  Návrhář tříd nepodporuje sjednocení (pouze množství potřebné pro Evropské unie největší datový člen je speciální typ třídy, ve kterém se přidělit paměť).  
  
## <a name="simple-inheritance"></a>Jednoduchá dědičnost  
Když přetažením více než jednu třídu na diagramu třídy a třídy mít vztah dědičnosti třídy, je šipka připojuje. Body šipku ve směru základní třídy. Například pokud následující třídy jsou zobrazeny v diagramu tříd, šipka připojuje, přejdete na příkaz b A:  
  
```cpp
class A {};  
class B : A {};  
```  
  
Můžete také přetáhněte pouze třídy B diagramu – třída, klikněte pravým tlačítkem na obrazec Třída pro B a pak klikněte na **zobrazit základní třídy**. Zobrazí se jeho základní třída: A.  
  
## <a name="multiple-inheritance"></a>Vícenásobná dědičnost  
Návrhář tříd podporuje vizualizaci dědičnosti tříd více relací. *Vícenásobná dědičnost* se používá při odvozené třídě má atributy více než jedné základní třídy. Tady je příklad více dědičnosti:  
  
```cpp
class Bird {};  
class Swimmer {};  
class Penguin : public Bird, public Swimmer {};  
```  
  
Když přetažením více než jednu třídu na diagramu tříd a třídy mít vztah dědičnosti více tříd, šipka je připojuje. Body šipku ve směru základní třídy.  
  
Pravým tlačítkem myši na obrazec třídy a pak levým na **zobrazit základní třídy** zobrazí pro vybrané třídy základní třídy.  
  
> [!NOTE]
>  **Zobrazit odvozené třídy** příkaz není podporován pro C++ – kód. Odvozené třídy můžete zobrazit tak, že přejdete na zobrazení tříd, rozbalení uzlu typu rozšíření **odvozené typy** podsložky a pak tyto typy přetažení na diagramu tříd.  
  
Další informace o dědičnosti více tříd, najdete v části [vícenásobná dědičnost](https://msdn.microsoft.com/en-us/library/6td5yws2.aspx) a [vícenásobné základní třídy](/cpp/cpp/multiple-base-classes).  
  
## <a name="abstract-classes"></a>Abstraktní třídy  
Návrhář tříd podporuje abstraktní třídy (i s názvem "základních tříd abstraktu"). Toto jsou třídy, které nikdy vytvořit instanci, ale ze kterého lze odvodit jiné třídy. Pomocí výše v tomto dokumentu příklad z "Vícenásobná dědičnost", může doložit `Bird` třídy jako jednotlivé objekty následujícím způsobem:  
  
```cpp
int main()  
{  
   Bird sparrow;  
   Bird crow;  
   Bird eagle;  
}  
```  
  
Však možné, že chcete vytvořit instanci `Swimmer` třída jako jednotlivé objekty. Možná chcete pouze k odvozování jiné typy zvířat třídy z něj, například `Penguin`, `Whale`, a `Fish`. V takovém případě by deklarovat `Swimmer` třídu jako abstraktní základní třídu.  
  
Chcete-li deklarovat jako abstraktní třídu, můžete použít `abstract` – klíčové slovo. Členové označené jako abstraktní, nebo součástí abstraktní třídu, virtuální a třídy, které jsou odvozeny od abstraktní třídu, musí být implementována.  
  
```cpp
class Swimmer abstract  
{  
   virtual void swim();  
   void dive();  
};  
```  
  
Je-li třídu deklarovat jako abstraktní také, včetně alespoň jeden čistý virtuální funkce:  
  
```cpp
class Swimmer  
{  
   virtual void swim() = 0;  
   void dive();  
};  
```  
  
Při zobrazení těchto deklarace v diagramu tříd, název třídy `Swimmer` a jeho čistou virtuální funkci `swim` v zobrazí v kurzíva v obrazce abstraktní třída společně s notace **abstraktní třída**. Všimněte si, že obrazce typu abstraktní třída je stejný jako běžné třídy, s tím rozdílem, že jeho ohraničení, je tečkovaná čára.  
  
Každý čistý virtuální funkci v základní třídě musí přepsat třídy odvozené od abstraktní základní třídu nebo nelze vytvořit instanci odvozené třídy. Ano, třeba při odvozování `Fish` třídy z `Swimmer` třídy, `Fish` musí přepsat `swim` metoda:  
  
```cpp
class Fish : public Swimmer  
{  
   void swim(int speed);  
};  
  
int main()  
{  
   Fish guppy;  
}  
```  
  
Když tento kód můžete zobrazit v diagramu tříd, návrhář tříd nakreslí řádku s dědičnost z `Fish` k `Swimmer`.  
  
## <a name="anonymous-classes"></a>Anonymní třídy  
Návrhář tříd podporuje anonymní třídy. *Anonymní typy třídy* jsou třídy deklarované bez identifikátor. Se nemůže mít konstruktor nebo destruktor, nelze předat jako argumenty funkce a nemůže být vrácen jako návratové hodnoty z funkcí. Anonymní třídu můžete použít k nahrazení název třídy s názvem typedef, jako v následujícím příkladu:  
  
```cpp
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
Struktury může být také anonymní. Návrhář tříd zobrazí anonymní třídy a struktury stejná jako zobrazení příslušného typu. I když lze deklarovat a zobrazit anonymní třídy a struktury, nebude používat návrhář tříd název značky, který určíte. Použije název, který generuje zobrazení tříd. Třídu nebo strukturu, se zobrazí v zobrazení tříd a návrhář tříd jako element názvem **__unnamed**.  
  
Další informace o anonymní třídy najdete v tématu [anonymní typy třídy](/cpp/cpp/anonymous-class-types).  
  
## <a name="template-classes"></a>Třídy šablon  
Návrhář tříd podporuje vizualizaci tříd šablon. Vnořené deklarace jsou podporovány. Následující tabulka uvádí některé typické deklarace.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`template <class T>`<br /><br /> `class A {};`|`A<T>`<br /><br /> Šablony třídy|  
|`template <class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> Šablony třídy|  
|`template <class T, int i>`<br /><br /> `class A {};`|`A<T, i>`<br /><br /> Šablony třídy|  
|`template <class T, template <class K> class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> Šablony třídy|  
V následující tabulce jsou uvedeny některé příklady částečná specializace.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`template<class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> Šablony třídy|  
|`template<class T>`<br /><br /> `class A<T, T> {};`|`A<T, T>`<br /><br /> Šablony třídy|  
|`template <class T>`<br /><br /> `class A<T, int> {};`|`A<T, int>`<br /><br /> Šablony třídy|  
|`template <class T1, class T2>`<br /><br /> `class A<T1*, T2*> {};`|`A<T1*, T2*>`<br /><br /> Šablony třídy|  
  
V následující tabulce jsou uvedeny některé příklady dědičnosti v částečná specializace.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`template <class T, class U>`<br /><br /> `class A {};`<br /><br /> `template <class TC>`<br /><br /> `class A<T, int> {};`<br /><br /> `class B : A<int, float>`<br /><br /> `{};`<br /><br /> `class C : A<int, int>`<br /><br /> `{};`|`A<T, U>`<br /><br /> Šablony třídy<br /><br /> `B`<br /><br /> Třída<br /><br /> (bodů na třídu)<br /><br /> `C`<br /><br /> Třída<br /><br /> (bodů na třídu)|  
  
Následující tabulka uvádí některé příklady částečná specializace šablony funkcí.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`class A`<br /><br /> `{`<br /><br /> `template <class T, class U>`<br /><br /> `void func(T a, U b);`<br /><br /> `template <class T>`<br /><br /> `void func(T a, int b);`<br /><br /> `};`|`A`<br /><br /> Func\<T, U > (+ 1 přetížení)|  
|`template <class T1>`<br /><br /> `class A {`<br /><br /> `template <class T2>`<br /><br /> `class B {};`<br /><br /> `};`<br /><br /> `template<> template<>`<br /><br /> `class A<type>::B<type> {};`|`A<T1>`<br /><br /> Šablony třídy<br /><br /> `B<T2>`<br /><br /> Šablony třídy<br /><br /> (B je obsažen v rámci třídy A v části **vnořené typy**)|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `class A : C<int> {};`|`A`<br /><br /> Třída<br /><br /> -> C\<int ><br /><br /> `C<T>`<br /><br /> Šablony třídy|  
  
Následující tabulka uvádí některé příklady dědičnosti šablony.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {`<br /><br /> `class B {};`<br /><br /> `}`<br /><br /> `class A : C<int>::B {};`|`A`<br /><br /> Třída<br /><br /> -> B<br /><br /> `C<int>`<br /><br /> Třída<br /><br /> (B je obsažen v rámci třídy C v části **vnořené typy**)<br /><br /> `C<T>`<br /><br /> Šablony třídy|  
  
V následující tabulce jsou uvedeny některé příklady kanonický Specializovaná třída připojení.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {};`<br /><br /> `class A : C<int> {};`<br /><br /> `class D : C<float> {};`|`A`<br /><br /> Třída<br /><br /> -> C\<int ><br /><br /> `C<int>`<br /><br /> Třída<br /><br /> `C<T>`<br /><br /> Šablony třídy<br /><br /> `D`<br /><br /> Třída<br /><br /> -> C\<float >|  
|`class B {`<br /><br /> `template <class T>`<br /><br /> `T min (const T &a, const T &b);`<br /><br /> `};`|`B`<br /><br /> minimální \<T >|  
  
## <a name="see-also"></a>Viz také
[Práce s kódem jazyka Visual C++](working-with-visual-cpp-code.md)   
[Třídy a struktury](/cpp/cpp/classes-and-structs-cpp)   
[Anonymní typy třídy](/cpp/cpp/anonymous-class-types)   
[Vícenásobná dědičnost](https://msdn.microsoft.com/en-us/library/6td5yws2.aspx)   
[Vícenásobné třídy Base](/cpp/cpp/multiple-base-classes)   
[Šablony](/cpp/cpp/templates-cpp)