---
redirect_url: /visualstudio/csharp-ide/refactoring/rename
title: "Refaktoring pro přejmenování (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Rename
- Rename refactoring [C#]
ms.assetid: 268942fc-b142-4dfa-8d90-bedd548c2e4f
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 42c5f99b3bf5ba95bc279cd5e117745ccc8e02c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="rename-refactoring-c"></a>Refaktoring pro přejmenování (C#)
**Přejmenujte** je refaktoringu funkce v sadě Visual Studio integrované vývojové prostředí (IDE), která poskytuje snadný způsob, jak přejmenovat identifikátory pro symboly kód například pole, místní proměnné, metody, obory názvů, vlastnosti a typy. **Přejmenujte** lze použít ke změně názvy v komentářích a v řetězcích a změnit deklarace a volání identifikátoru.  
  
> [!NOTE]
>  Při použití správy zdrojového kódu pro Visual Studio, získáte nejnovější verzi zdrojů, než se pokusíte provést refaktoring přejmenovat.  
  
 Refaktoring přejmenování má k dispozici následující funkce sady Visual Studio:  
  
|Funkce|Chování refaktoring v prostředí IDE|  
|-------------|----------------------------------------|  
|Editor kódu|V editoru kódu refaktoringu přejmenování je dostupná, když umístěte kurzor na určité typy kódu symbolů. Pokud se ukazatel na této pozici, můžete vyvolat **přejmenovat** příkaz zadáním klávesové zkratky (Ctrl + R, Ctrl + R) nebo výběrem **přejmenovat** příkaz rychlé akce, místní nabídky, nebo **Refaktorovat** nabídky.|  
|zobrazení tříd|Když vyberete identifikátorem v zobrazení tříd, přejmenování Refaktoring je k dispozici v místní nabídce a **Refaktorovat** nabídky.|  
|prohlížeč objektů|Když vyberete identifikátorem v prohlížeči objektů, přejmenování Refaktoring je k dispozici pouze z **Refaktorovat** nabídky.|  
|Vlastnost mřížku Návrhář formulářů Windows|V **mřížkou vlastností** z Návrhář formulářů Windows změnit název ovládacího prvku zahájí operaci přejmenovat pro ovládací prvek. **Přejmenovat** dialogové okno se nezobrazí.|  
|Průzkumník řešení|V **Průzkumníku řešení**, **přejmenovat** příkaz je k dispozici v místní nabídce. Vybraný zdrojový soubor obsahuje třídu, jejíž název třídy je stejný jako název souboru, můžete tento příkaz současně přejmenujte zdrojový soubor a provést refaktoring přejmenovat.<br /><br /> Pokud chcete vytvořit výchozí aplikaci systému Windows a pak přejmenujte Form1.cs TestForm.cs, například název zdrojového souboru Form1.cs se změní na TestForm.cs a třída Form1 a všech odkazech na, že třída bude přejmenován na TestForm. **Poznámka:** **vrátit zpět** pouze zruší přejmenování refaktoring v kódu a není změnu názvu souboru zpět na původní název příkazu (CTRL + Z). <br /><br /> Pokud vybraný zdrojový soubor neobsahuje třídu, jejíž název je stejný jako název souboru **přejmenovat** v **Průzkumníku řešení** pouze přejmenuje zdrojový soubor a nebude provést přejmenování refaktoring.|  
  
## <a name="rename-operations"></a>Operace přejmenování  
 Při spuštění **přejmenovat**, jak je popsáno v následující tabulce se provede konkrétní operace přejmenování pro každý symbol kódu refaktoringu modul.  
  
|Symbol v kódu|Operace přejmenování|  
|-----------------|----------------------|  
|Pole|Deklarace a použití pole se změní na nový název.|  
|místní proměnné|Deklarace a použití proměnné se změní na nový název.|  
|Metoda|Název metody a všechny odkazy na dané metody se změní na nový název. **Poznámka:** při přejmenování metody rozšíření operaci přejmenování rozšíří na všechny instance metody, které jsou v oboru, bez ohledu na to, zda rozšíření metody slouží jako statickou metodu nebo metody instance. Další informace najdete v tématu [rozšiřující metody](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods).|  
|Obor názvů|Název oboru názvů se změní na nový název v deklaraci, všechny `using` příkazy a plně kvalifikované názvy. **Poznámka:** při přejmenování obor názvů, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rovněž aktualizuje **výchozí Namespace** vlastnost **aplikace** stránky **Návrhář projektu**. Tuto vlastnost nelze resetovat výběrem **vrátit zpět** z **upravit** nabídky. Chcete-li obnovit **výchozí Namespace** hodnotu vlastnosti, musíte upravit vlastnosti v **Návrhář projektu**. Další informace najdete v tématu [stránky aplikace](../ide/reference/application-page-project-designer-csharp.md).|  
|Vlastnost|Deklarace a použití vlastnosti se změní na nový název.|  
|Typ|Změní na nový název, včetně konstruktory a destruktory všechny deklarace a všechny použití typu. Pro částečné typy operaci přejmenování rozšíří na všechny části.|  
  
#### <a name="to-rename-an-identifier"></a>Chcete-li přejmenovat identifikátor  
  
1.  Vytvořte konzolovou aplikaci s názvem `RenameIdentifier`a potom můžete nahradit `Program` s následující příklad kódu.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  Umístěte kurzor na `MethodB`, buď v deklarace metody nebo volání metody.  
  
3.  Z **Refaktorovat** nabídce vyberte možnost **přejmenovat**. **Přejmenovat** zobrazí se dialogové okno.  
  
     Můžete také kliknout pravým tlačítkem kurzor, přejděte na příkaz **Refaktorovat** v místní nabídce a pak klikněte na tlačítko **přejmenovat** zobrazíte **přejmenovat** dialogové okno.  
  
4.  V **nový název** zadejte `MethodC`.  
  
5.  Vyberte **vyhledávání v komentářích** zaškrtávací políčko.  
  
6.  Click **OK**.  
  
7.  V **zobrazení náhledu změn** dialogové okno, klikněte na tlačítko **použít**.  
  
#### <a name="to-rename-an-identifier-using-quick-actions"></a>Chcete-li přejmenovat identifikátor pomocí rychlé akce  
  
1.  Vytvořte konzolovou aplikaci s názvem `RenameIdentifier`a potom můžete nahradit `Program` s následující příklad kódu.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  V deklaraci pro `MethodB`, zadejte nebo backspace přes identifikátor metoda. Žárovky rychlé akce se zobrazí u okraje.  
  
    > [!NOTE]
    >  Pouze můžete vyvolat přejmenování refaktoring pomocí rychlé akce na deklarace identifikátoru.  
  
3.  Zadejte klávesovou zkratku **Shift + Alt + F10** zobrazení nabídky rychlé akce.  
  
     -nebo-  
  
     Klikněte na černý trojúhelník vedle žárovky zobrazení nabídky rychlé akce.  
  
4.  Vyberte **přejmenovat '\<identifer1 >' do '\<identifier2 >'** položku nabídky k vyvolání refaktoring přejmenovat. Všechny odkazy na  **\<identifer1 >** se automaticky aktualizují na  **\<identifier2 >**.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="renaming-implemented-or-overridden-members"></a>Přejmenování implementovaná nebo přepsané členů  
 Pokud jste **přejmenovat** člena, který implementuje nebo přepsání nebo je implementována nebo přepsat členy v jiných typech [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zobrazí dialogové okno s upozorněním, operace přejmenování způsobí kaskádové aktualizace. Pokud kliknete na tlačítko **pokračovat**, refaktoringu rekurzivně modul vyhledá a přejmenuje všechny členy v základní a odvozené typy, které mají implementuje nebo přepsání relace se členem je přejmenovat.  
  
 Následující příklad kódu obsahuje členy se implementuje nebo přepsání vztahy.  
  
 [!code-csharp[CsUsingCsIDERefactor#1](../csharp-ide/codesnippet/CSharp/rename-refactoring-csharp_1.cs)]  
  
 V předchozím příkladu přejmenování `C.Method()` také přejmenuje `Ibase.Method()` protože `C.Method()` implementuje `Ibase.Method()`. V dalším kroku, uvidí rekurzivně modul refactor `Ibase.Method()` je implementováno modulem `Derived.Method()` a přejmenuje `Derived.Method()`. Modul refactor nepřejmenuje `Base.Method()`, protože `Derived.Method()` nepřepisuje `Base.Method()`. Modul refaktoringu zastaví sem, pokud nemáte **přejmenovat přetížení** změnami **přejmenovat** dialogové okno.  
  
 Pokud **přejmenovat přetížení** je zaškrtnuto, přejmenuje modul refactor `Derived.Method(int i)` vzhledem k tomu, že ho přetížení `Derived.Method()`, `Base.Method(int i)` vzhledem k tomu, že je přepsána `Derived.Method(int i)`, a `Base.Method()` vzhledem k tomu, že je přetížení `Base.Method(int i)`.  
  
> [!NOTE]
>  Při přejmenování člena, který byl definován v odkazovaném sestavení, dialogové okno vysvětluje, že přejmenování způsobí chyby sestavení.  
  
## <a name="renaming-properties-of-anonymous-types"></a>Přejmenování vlastnosti anonymní typy  
 Pokud přejmenujete na vlastnost ve anonymní typy, operace přejmenování rozšíří na vlastnosti v jiných anonymní typy, které mají stejné vlastnosti. Následující příklady znázorňují toto chování.  
  
```csharp  
var a = new { ID = 1};  
var b = new { ID = 2};  
```  
  
 V předchozím kódu přejmenování `ID` změní `ID` v obou příkazů protože mají stejné základní anonymního typu.  
  
```csharp  
var companyIDs =  
    from c in companylist  
    select new { ID = c.ID, Name = c.Name};  
  
var orderIDs =  
    from o in orderlist  
    select new { ID = o.ID, Item = o.Name};  
```  
  
 V předchozím kódu přejmenování `ID` přejmenuje pouze jednu instanci `ID` protože `companyIDs` a `orderIDs` nemají stejné vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](refactoring-csharp.md)   
 [Anonymní typy](/dotnet/csharp/programming-guide/classes-and-structs/anonymous-types)