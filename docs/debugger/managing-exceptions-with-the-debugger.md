---
title: "Správa výjimek pomocí ladicího programu sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 04/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.exceptions
- vs.debug.exceptions.find
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- run-time errors
- exception handling, during debugging
- errors [debugger]
- debugger, runtime errors
- On Error-style error handlers
- exceptions, Win32
- run-time errors, debugging
- Win32, exceptions
- run time, exceptions
- error handling
- debugging [Visual Studio], exception handling
- common language runtime, exceptions
- native run-time checks
- exceptions, debugging
ms.assetid: 43a77fa8-37d0-4c98-a334-0134dbca4ece
caps.latest.revision: "35"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c04934aed17c6e1b00664d371ff591ebbc3486a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="manage-exceptions-with-the-debugger-in-visual-studio"></a>Správa výjimek pomocí ladicího programu v sadě Visual Studio

Výjimkou je to znamenat stav chyby, ke kterému dochází, když se program spouští. Ladicí program můžete zjistit, které výjimky (nebo sady výjimek) na přerušení na a na bod, který chcete, aby ladicí program na přerušení (když dělí ladicího programu, jeho ukazuje, kde byla výjimka vydána). Můžete také přidat nebo odstranit výjimky. S řešením otevřete v sadě Visual Studio, použijte **ladění > Windows > Nastavení výjimky** otevřete **nastavení výjimky** okno. 

Můžete a měl by poskytnout obslužné rutiny, které reagují na nejdůležitější výjimky, ale je důležité vědět, jak nakonfigurovat ladicí program na vždy přerušení spuštění pro některé výjimky.
  
Když dojde k výjimce, ladicího programu zapíše zprávu výjimky do okna výstupu. Spuštění se může přerušit v následujících případech:  
  
-   Když výjimku je vyvolána a není zpracován.  
  
-   Když ladicí program nastaven tak, aby před vyvoláním všechny obslužné rutiny přerušení spuštění.  
  
-   Pokud jste nastavili [pouze můj kód](../debugger/just-my-code.md), a ladicí program je nakonfigurováno na přerušení na všechny výjimka, která nejsou zpracovávány v uživatelského kódu.  
  
> [!NOTE]
>  Technologie ASP.NET má obslužnou rutinu výjimky nejvyšší úrovně, která zobrazuje chybové stránky v prohlížeči. Nezalamuje spuštění, pokud **pouze můj kód** je zapnutý. Příklad, naleznete v části [nastavení ladicího programu pokračoval na výjimky neošetřené uživatelem](../debugger/managing-exceptions-with-the-debugger.md#BKMK_UserUnhandled) níže.  
  
> [!NOTE]
>  V aplikaci Visual Basic ladicí program spravuje všechny chyby jako výjimky, i když používáte obslužných rutin chyba stylu chyby.    
  
## <a name="tell-the-debugger-to-break-when-an-exception-is-thrown"></a>Řekněte ladicí program na přerušení při vyvolání k výjimce  
Ladicí program může dojít k narušení provádění v okamžiku, kdy je vyvolána výjimka, s možností prozkoumat výjimka před vyvoláním obslužnou rutinu.  
  
V **nastavení výjimky** okno (**ladění > Windows > Nastavení výjimky**), rozbalte uzel pro kategorii výjimek (například **běžné výjimky za běhu jazyka**, což znamená výjimky .NET) a zaškrtněte políčko pro konkrétní výjimky v rámci této kategorie (například **System.AccessViolationException**). Můžete také vybrat celou kategorii výjimky.  
  
![Zaškrtnutí AccessViolationException](../debugger/media/exceptionsettingscheckaccess.png "ExceptionSettingsCheckAccess")  

> [!TIP]
> Specifických výjimek můžete najít pomocí **vyhledávání** okno v **nastavení výjimky** nástrojů, nebo použijte vyhledávání k filtrování pro konkrétní obory názvů (například **System.IO**).
  
Pokud jste vybrali k výjimce v **nastavení výjimky** okně spuštění ladicího programu poruší bez ohledu na je vyvolána výjimka, bez ohledu na to, jestli je zpracovává nebo neošetřená. Výjimka v tomto okamžiku se nazývá první odpovídající výjimce. Například tady je několik scénářů:  
  
*  V následující C# aplikaci konzoly, vyvolá metoda Main **AccessViolationException** uvnitř `try/catch` bloku:  
  
    ```CSharp  
    static void Main(string[] args)  
    {  
        try  
        {  
            throw new AccessViolationException();  
            Console.WriteLine("here");  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("caught exception");  
        }  
        Console.WriteLine("goodbye");  
    }  
    ```  
  
     Pokud máte **AccessViolationException** změnami **nastavení výjimky**, při spuštění tohoto kódu při provádění ladicí program bude rozdělit na `throw` řádku. Pak můžete pokračovat v provádění. Konzola by měl zobrazit i řádky:  
  
    ```  
    caught exception  
    goodbye  
    ```  
  
     nejsou zde uvedeny, ale `here` řádku.  
  
*  Konzolovou aplikaci C# odkazuje na knihovny tříd s třídu, která má dvě metody, metodu, vyvolá výjimku, která ji zpracovává a druhý metoda, která vyvolala výjimku stejné a nemůže pracovat:  
  
    ```csharp 
    public class Class1  
    {  
        public void ThrowHandledException()  
        {  
            try  
            {  
                throw new AccessViolationException();  
            }  
            catch (AccessViolationException ave)  
            {  
                Console.WriteLine("caught exception" + ave.Message);  
            }  
        }  
  
        public void ThrowUnhandledException()  
        {  
            throw new AccessViolationException();  
        }  
    }  
    ```  
  
     Tady je metoda Main() aplikace konzoly:  
  
    ```CSharp  
    static void Main(string[] args)  
    {  
        Class1 class1 = new Class1();  
        class1.ThrowHandledException();  
        class1.ThrowUnhandledException();  
    }  
    ```  
  
     Pokud máte **AccessViolationException** změnami **nastavení výjimky**, při spuštění tohoto kódu při provádění ladicí program bude rozdělit na `throw` řádku v obou  **ThrowHandledException()** a **ThrowUnhandledException()**.  
  
 Pokud chcete obnovit výchozí hodnoty nastavení výjimky, můžete kliknout **obnovení** na panelu nástrojů zobrazí tlačítko:  
  
 ![Obnovit výchozí nastavení v nastavení výjimky](../debugger/media/restoredefaultexceptions.png "RestoreDefaultExceptions")  
  
##  <a name="BKMK_UserUnhandled"></a>Řekněte ladicí program na pokračovat při výjimkách neošetřených uživatelem  
 Pokud ladíte .NET nebo JavaScript kód s [pouze můj kód](../debugger/just-my-code.md), se dá zjistit ladicího programu není na přerušení na výjimky, které nejsou zpracovány v uživatelském kódu, ale jsou zpracovávány jinde.  
  
1.  V **nastavení výjimky** okno, otevřete v místní nabídce kliknete pravým tlačítkem do okna a potom výběrem **zobrazit sloupce**. (Pokud jste vypnuli **pouze můj kód**, tento příkaz nezobrazí.)  
  
2.  Měli byste vidět druhý sloupec s názvem **další akce**. V tomto sloupci se zobrazuje **pokračovat v případě neošetřené pomocí uživatelského kódu** na konkrétních výjimek, což znamená, že ladicí program nezalamuje Pokud této výjimky nejsou zpracovávány v uživatelském kódu, ale je zpracována v externí kódu.  
  
3.  Můžete změnit toto nastavení, buď pro konkrétní výjimky (vyberte výjimku, klikněte pravým tlačítkem a vyberte nebo zrušte výběr **pokračovat v případě neošetřené v uživatelském kódu**) nebo pro celý druh výjimky (například všechny nejběžnější Výjimky za běhu jazyka).  
  
 Například webové aplikace ASP.NET zpracování výjimek převedením na stavový kód HTTP 500 ([zpracování výjimek v rozhraní API ASP.NET](http://www.asp.net/web-api/overview/error-handling/exception-handling)), který nemusí vám pomůže určit zdroj výjimky. V následujícím příkladu uživatelský kód zavolá `String.Format()` , vyvolá <xref:System.FormatException>. Provádění dělí takto:  
  
 ![zalomení na uživatele & č. 45; výjimka unhanlded](../debugger/media/exceptionunhandledbyuser.png "ExceptionUnhandledByUser")  
  
## <a name="add-and-delete-exceptions"></a>Přidávání a odstraňování výjimek  
 Můžete přidat a odstranit výjimky. Odstraněním libovolného typu výjimka kategorie výjimka výběrem a kliknutím na **odstranit** na tlačítko (znaménka minus) **nastavení výjimky** panelu nástrojů nebo kliknete pravým tlačítkem na výjimku a Výběr **odstranit** v místní nabídce. Odstraňování výjimku má stejný účinek jako s výjimkou není zaškrtnuto, což je, že nebudou porušovat ladicí program, když je vyvolána.  
  
 Přidat výjimku: v **nastavení výjimky** okno, vyberte jednu z výjimka kategorie (například **modul Common Language Runtime**) a klikněte na tlačítko **přidat** tlačítko. Zadejte název výjimky (například. **System.UriTemplateMatchException**). Výjimka je přidán do seznamu (v abecedním pořadí) a automaticky kontroluje.  
  
 Pokud chcete přidat výjimku výjimky přístupu paměti grafického procesoru, výjimek jazyka JavaScript Runtime nebo výjimky Win32 kategorií, budete muset zahrnují kód chyby a také popis.  
  
> [!TIP]
>  Zkontrolujte zadané informace! **Nastavení výjimky** okno neohlásí přítomnost přidané výjimky. Pokud zadáte **Sytem.UriTemplateMatchException**, získáte položku pro této výjimky (a ne pro **System.UriTemplateMatchException**).  
  
 Nastavení výjimky jsou v souboru .suo na řešení, nastavené jako trvalé, takže se vztahují na konkrétní řešení. Nelze znovu použít nastavení konkrétní výjimky v řešeních. V tomto okamžiku pouze přidané výjimky jsou nastavené jako trvalé; odstraněné výjimky nejsou. Jinými slovy můžete přidat výjimku, zavřete a znovu otevřete řešení a výjimka bude stále existovat. Ale pokud odstraníte výjimku a zavřete řešení znovu otevřít, se znovu zobrazí výjimka.  
  
 **Nastavení výjimky** okno podporuje typy obecné výjimek v jazyce C#, ale není v jazyce Visual Basic. Na přerušení na výjimky jako `MyNamespace.GenericException<T>`, je nutné přidat výjimku jako **MyNamespace.GenericException'1**. To znamená pokud jste vytvořili výjimku takto:  
  
```CSharp  
public class GenericException<T> : Exception  
{  
    public GenericException() : base("This is a generic exception.")  
    {  
    }  
}  
```  
  
 Můžete přidat výjimku **nastavení výjimky** podobné výjimky:  
  
 ![Přidání obecné výjimky](../debugger/media/addgenericexception.png "AddGenericException")  

## <a name="add-conditions-to-an-exception"></a>Přidání podmínek do výjimku

Můžete nastavit podmínky, na výjimky v **nastavení výjimky** dialogové okno. Aktuálně podporované podmínky zahrnují názvy modulu pro zahrnutí nebo vyloučení pro výjimku. Nastavením názvy modulů jako podmínky můžete rozdělit pro výjimky pouze na konkrétní kódové moduly nebo se můžete vyhnout narušující na konkrétní moduly.

> [!NOTE]
> Přidání podmínek do výjimku je nového v[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Chcete-li přidat podmíněného výjimky, zvolte **upravit podmínky** ikona v dialogovém okně Nastavení výjimky nebo klikněte pravým tlačítkem na výjimku a zvolte **upravit podmínky**.

![Podmínky se u výjimku](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")
  
## <a name="see-also"></a>Viz také  
 [Pokračování v provádění po výjimce](../debugger/continuing-execution-after-an-exception.md)   
 [Postupy: Kontrola systémového kódu po výjimce](../debugger/how-to-examine-system-code-after-an-exception.md)   
 [Postupy: použití nativních kontrol za běhu](../debugger/how-to-use-native-run-time-checks.md)   
 [Run-Time zkontroluje bez běhové knihovny jazyka C](../debugger/using-run-time-checks-without-the-c-run-time-library.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)