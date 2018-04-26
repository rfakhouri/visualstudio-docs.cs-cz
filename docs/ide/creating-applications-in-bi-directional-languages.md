---
title: Vytváření aplikací v obousměrných jazycích
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Hebrew character display, creating applications
- bi-directional language support, about bi-directional language support
- Arabic language, creating applications
ms.assetid: b56f9795-ed8d-4452-9d49-8ca0b0145d86
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 576e1f715e1196e7e0b774698fe45b550a1313f8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="creating-applications-in-bi-directional-languages"></a>Vytváření aplikací v obousměrných jazycích

Visual Studio můžete vytvářet aplikace, které správně zobrazovat text v jazycích, které jsou zapsány-doleva, včetně arabština a hebrejština. Pro některé funkce můžete jednoduše nastavit vlastnosti. V ostatních případech je nutné implementovat funkce v kódu.

> [!NOTE]
> Chcete-li zadat a zobrazit obousměrné jazyky, musíte pracovat s verzí systému Windows, který je nakonfigurovaný s příslušný jazyk. To může být buď anglickou verzi systému Windows pomocí příslušné jazykové sady nainstalovaná nebo správně lokalizované verzi systému Windows.

## <a name="types-of-application-that-support-bi-directional-languages"></a>Typy aplikací, které podporují obousměrné jazyky

-  Aplikace systému Windows. Můžete vytvořit plně obousměrnou aplikace, které zahrnují podporu pro obousměrný text, zprava doleva pořadí čtení a zrcadlení (Prohodit rozložení windows, nabídek, dialogová okna a tak dále). S výjimkou zrcadlení, tyto funkce jsou dostupné ve výchozím nastavení nebo nastavení vlastností. Zrcadlení se podporuje ze své podstaty pro některé funkce, například okna zpráv. Ale v ostatních případech musí implementovat zrcadlení v kódu. Další informace najdete v tématu [obousměrná podpora pro aplikace Windows Forms](http://msdn.microsoft.com/Library/7b622fa4-f390-4e4d-b624-83a1917cccf2).

-  Webové aplikace. Webové služby podpory a příjem odesílání textu ve formátu UTF-8 a Unicode, která je vhodná pro aplikace, zahrnující obousměrných jazycích. Klientských webových aplikací spoléhají na prohlížeči pro uživatelské rozhraní, tak, aby závisí na tom, jak dobře prohlížeče uživatele podporuje tyto funkce obousměrný stupeň obousměrná podpora ve webové aplikaci. V sadě Visual Studio můžete vytvořit aplikace s podporou pro arabštinu nebo hebrejštinu text, čtení zprava doleva pořadí, kódování souborů a nastavení místní jazykovou verzi. Další informace najdete v tématu [obousměrná podpora pro webové aplikace ASP.NET](http://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03).

-  Konzolové aplikace. Konzolové aplikace nebudou obsahovat text podpora obousměrných jazycích. Toto je v důsledku toho, jak funguje Windows pomocí konzolové aplikace.

## <a name="visual-studio-features-that-are-fully-supported"></a>Visual Studio funkce, které jsou plně podporovány
 V době návrhu v sadě Visual Studio můžete použít obousměrných jazycích těmito způsoby:

-   **Vstupní text** Visual Studio podporuje kódování Unicode, takže když systém je nastaven na příslušné národní prostředí a jazyk, můžete zadat text v arabské nebo hebrejštinu. (Podpora Arabic zahrnuje kašidy a diakritiky.)

-   **Názvy objektů** obousměrné jazyky můžete přiřadit názvy řešení, projekty, soubory, složky a tak dále. V kódu můžete obousměrných jazycích pro názvy proměnných, třídy, objekt, atributy, metadat a dalších prvků.

-   **Kódování souborů** můžete uložit a otevřít soubory s konkrétní jazyk nebo kódování Unicode. Další informace najdete v tématu [postupy: ukládání a otevírání souborů s kódováním](../ide/how-to-save-and-open-files-with-encoding.md).

## <a name="features-with-limited-or-no-support"></a>Funkce s omezeným nebo bez podpory
 Další funkce, které jsou společné pro obousměrná jazyková aplikace nejsou plně podporovány v sadě Visual Studio, nebo v některých případech vůbec. Mezi ně patří:

**Doleva pořadí čtení** ve výchozím nastavení, použijte ovládací prvky zadávání textu, použijte v sadě Visual Studio pořadí čtení zleva doprava. Ve většině případů můžete použít standardní Windows gesta přepnout pořadí čtení. Například můžete stisknout **Ctrl + RightShift** přepnout **vlastnosti** okna pro podporu čtení zprava doleva pořadí pro hodnoty vlastností.

Čtení zprava doleva pořadí však není podporováno everywhere v sadě Visual Studio. Mezi výjimky patří:

-   Zaškrtávací políčka, rozevírací seznamy a jiných ovládacích prvků v sadě Visual Studio dialogových oknech vždy použijte pořadí čtení zleva doprava.

-   Editor kódu (a textovém editoru) nepodporuje pořadí čtení zprava doleva. Můžete zadat text v jazyce obousměrný, ale pořadí čtení je vždy zleva doprava.

## <a name="naming-things-using-arabic-or-hebrew-text"></a>Pojmenování věcí pomocí arabské nebo hebrejštinu textu
 Arabština nebo hebrejštinu text můžete přiřadit názvy složek, proměnné nebo jiné objekty. Při práci s arabština, můžete použít znaky Arabic včetně kašidy a znaky s diakritikou.

 Tyto prvky můžete pojmenovat pomocí arabské nebo hebrejštinu a bude zpracována správně v sadě Visual Studio:

-   Řešení, projektu a názvy souborů, včetně všechny složky, která zahrnete cesta k projektu. **Průzkumník řešení** se zobrazí názvy řešení a element správně.

-   Obsah souboru. Můžete otevřít nebo uložit soubory s kódováním Unicode nebo vybraný úsek kódu stránky.

    > [!NOTE]
    >  Editor kódu je zvláštní případ. Podrobnosti najdete v tématu níže.

-   Datové prvky. **V Průzkumníku serveru** zobrazí tyto prvky správně a umožní je upravit.

-   Elementy zkopírován do schránky systému Windows.

-   Atributy a metadata.

-   Hodnoty vlastností. Můžete použít arabské nebo hebrejštinu textu v **vlastnosti** okno. Okno umožňuje přepínat mezi pořadí čtení zprava doleva a zleva doprava pomocí standardní stisknutí kláves systému Windows (**Ctrl + RightShift** pro doleva, a **Ctrl + LeftShift** pro zleva doprava).

-   Kód a prostý text. V editoru kódu (což je také textovém editoru) arabské nebo hebrejštinu můžete použít název třídy, funkce, proměnné, vlastnosti, textové literály, atributy a tak dále. Editor však nepodporuje pořadí čtení zprava doleva. text začíná vždy na levý okraj.

    > [!TIP]
    > Doporučujeme umístit textové literály soubory prostředků místo pevně kódováno je do aplikací. Další informace najdete v tématu [prostředky v aplikacích klasické pracovní plochy (rozhraní .NET Framework)](/dotnet/framework/resources/index).

    > [!NOTE]
    > Musíte být konzistentní v tom, jak odkazovat na objekty s názvem v těchto jazycích. Pokud používáte kašida v pojmenování Arabic proměnné, je vždy nutné použít kašida k odkazování na tuto proměnnou nebo dojde k chybám.

-   Komentáře kódu. Komentáře můžete vytvořit v arabské nebo hebrejštinu. Můžete taky těchto jazyků v nástroji Tvůrce komentář.

## <a name="see-also"></a>Viz také

- [Obousměrná podpora pro aplikace Windows Forms](/dotnet/framework/winforms/advanced/bi-directional-support-for-windows-forms-applications)
- [Obousměrná podpora pro webové aplikace ASP.NET](http://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03)
- [Globalizace aplikací](../ide/globalizing-applications.md)
- [Lokalizace aplikací](../ide/localizing-applications.md)