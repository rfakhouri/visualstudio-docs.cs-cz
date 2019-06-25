---
title: Podpora pro aplikace pro arabština a hebrejština
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Hebrew character display, creating applications
- bidirectional language support, about bidirectional language support
- Arabic language, creating applications
ms.assetid: b56f9795-ed8d-4452-9d49-8ca0b0145d86
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d09ad8644c30be76c38cf4b819d09ee1c470cb39
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62793436"
---
# <a name="create-applications-in-bidirectional-languages"></a>Vytváření aplikací v obousměrných jazycích

Visual Studio můžete vytvářet aplikace pro správné zobrazení textu v jazycích napsané-doleva, včetně arabština a hebrejština. Pro některé funkce stačí nastavit vlastnosti. V ostatních případech je nutné implementovat v kódu funkce.

> [!NOTE]
> Pokud chcete zadat a zobrazit obousměrných jazyků, musíte pracovat s verzí Windows, který je nakonfigurován příslušný jazyk. To může být buď anglickou verzi systému Windows s odpovídající jazyková sada nainstalovaná nebo správně lokalizovanou verzi Windows.

## <a name="types-of-applications-that-support-bidirectional-languages"></a>Typy aplikací, které podporují obousměrné jazyky

- Aplikace Windows

   Můžete vytvořit plně obousměrné aplikace, které zahrnují podporu pro obousměrný text zprava doleva pořadí čtení a zrcadlení (reverzní rozložení windows, nabídek, dialogová okna a tak dále). S výjimkou zrcadlení, tyto funkce jsou dostupné ve výchozím nastavení nebo nastavení vlastností. Zrcadlení se podporuje ze své podstaty pro některé funkce, jako jsou okna se zprávou. Ale v ostatních případech je nutné implementovat zrcadlení v kódu. Další informace najdete v tématu [obousměrná podpora pro aplikace Windows Forms](/dotnet/framework/winforms/advanced/bi-directional-support-for-windows-forms-applications).

- Webové aplikace

   Webové služby podporují odesílání a přijímání UTF-8 a text v kódu Unicode, díky kterým jsou vhodné pro aplikace, které se týkají obousměrných jazyků. Webové klientské aplikace závisí na prohlížeče pro jeho uživatelské rozhraní, takže stupeň obousměrná podpora v webové aplikace závisí na tom, jak dobře webového prohlížeče podporuje tyto funkce obousměrné. V sadě Visual Studio můžete vytvářet aplikace s podporou arabský nebo hebrejský text, pořadí čtení zprava doleva, kódování souborů a nastavení místní jazykové verze. Další informace najdete v tématu [obousměrná podpora pro webové aplikace ASP.NET](https://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03).

Aplikace konzoly nezahrnují text podpora obousměrných jazyků. Toto je v důsledku toho, jak funguje Windows pomocí konzolové aplikace.

## <a name="fully-supported-features"></a>Plně podporované funkce

V době návrhu v sadě Visual Studio můžete použít obousměrné jazyky následujícími způsoby:

- **Zadání textu**

   Visual Studio podporuje kódování Unicode, takže když systém je nastaven na odpovídající národní prostředí a jazyk, můžete zadat text ve arabské nebo hebrejské. (Arabské podpora zahrnuje kašidy a diakritických znamének.)

- **Názvy objektů**

   Obousměrné jazyky můžete přiřadit názvy řešení, projekty, soubory, složky a tak dále. V kódu můžete použít obousměrné jazyky pro názvy proměnných, tříd, objektů, atributy, metadata a další prvky.

- **Kódování souboru**

   Můžete uložit a otevírání souborů se konkrétní jazyk nebo kódování Unicode. Další informace najdete v tématu [jak: Ukládání a otevírání souborů s kódováním](../ide/how-to-save-and-open-files-with-encoding.md).

## <a name="features-with-limited-support"></a>Funkce s omezenou podporou

### <a name="right-to-left-reading-order"></a>Pořadí čtení zprava doleva

Ve výchozím nastavení použijte ovládací prvky textového vstupu v sadě Visual Studio pořadí čtení zleva doprava. Ve většině případů můžete použít standardní Windows gesta přepnout pořadí čtení. Například můžete stisknout **Ctrl**+**RightShift** přepnout **vlastnosti** okna pro podporu hodnoty vlastností pořadí čtení zprava doleva. Pořadí čtení zprava doleva se však nepodporuje všude v sadě Visual Studio:

- Zaškrtávací políčka, rozevírací seznamy a další ovládací prvky v dialogových oknech sady Visual Studio použijte vždy pořadí čtení zleva doprava.

- Editor kódu (a textový editor) nepodporuje pořadí čtení zprava doleva. Můžete zadat text v jazyce obousměrný, ale je vždy o pořadí čtení zleva doprava.

## <a name="arabic-or-hebrew-object-names"></a>Arabský nebo hebrejský názvy objektů

Arabský nebo hebrejský text můžete přiřadit názvy složek, proměnné nebo jiné objekty. Při práci s arabština, můžete použít libovolný Arabské znaků včetně kašidy a diakritických znamének.

Tyto prvky můžete být pojmenované pomocí arabské nebo hebrejské a jsou správně zpracovány v sadě Visual Studio:

- Řešení, projektů a názvy souborů, včetně některou ze složek, které jsou v cestě projektu. **Průzkumník řešení** správně zobrazuje řešení a názvy elementů.

- Obsah souboru. Můžete otevřít nebo uložit soubory s kódováním Unicode nebo s vybranou znakovou stránkou.

    > [!NOTE]
    > Editor kódu nepodporuje pořadí čtení zprava doleva.

- Datové prvky. **Průzkumník serveru** správně zobrazuje tyto prvky a umožňuje upravovat.

- Prvky zkopírováno do schránky Windows.

- Atributy a metadata.

- Hodnoty vlastností. Arabský nebo hebrejský text v můžete použít **vlastnosti** okna. V okně umožňuje přepínat mezi pořadí čtení zprava doleva a doprava a doleva pomocí standardních klávesových úhozů Windows (**Ctrl**+**RightShift** zprava doleva a **Ctrl**+**LeftShift** pro zleva doprava).

- Kód a text literálu. V editoru kódu vám pomůže arabské nebo hebrejské název třídy, funkce, proměnné, vlastnosti, řetězcové literály, atributy a tak dále. Editor ale nepodporuje pořadí čtení zprava doleva. text vždy začíná na levém okraji.

    > [!TIP]
    > Byste měli umístit řetězcové literály do souborů prostředků místo pevného kódování je do vašich aplikací. Další informace najdete v tématu [prostředky v aplikacích klasické pracovní plochy (.NET Framework)](/dotnet/framework/resources/index).

    > [!NOTE]
    > Musíte být konzistentní vzhledem k aplikacím v jak odkazovat na objekty s názvem v arabština a hebrejština. Například pokud používáte kašidy názvů Arabské proměnné, musíte vždycky použít kašida k odkazování na, že bude výsledek proměnné nebo chyby.

- Komentáře ke kódu. Vytvoření komentářů v arabské nebo hebrejské. Můžete také těchto jazyků v nástroji Tvůrce komentář.