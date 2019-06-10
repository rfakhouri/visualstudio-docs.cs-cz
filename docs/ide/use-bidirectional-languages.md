---
title: Podpora pro arabština a hebrejština
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Hebrew character display [Visual Studio]
- bidirectional language support
- Arabic, creating applications
ms.assetid: b56f9795-ed8d-4452-9d49-8ca0b0145d86
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1271e5160920dc79decc9acc98aa1e5e3d936ca5
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/10/2019
ms.locfileid: "66823563"
---
# <a name="support-for-bidirectional-languages-in-visual-studio"></a>Podpora obousměrných jazyků v sadě Visual Studio

Visual Studio arabština a hebrejština text můžete zobrazit správně a umožňuje zadat obousměrný text pro objekt názvy a hodnoty.

> [!NOTE]
> Pokud chcete zadat a zobrazit obousměrných jazyků, musíte pracovat s verzí Windows, který je nakonfigurován příslušný jazyk. To může být buď anglickou verzi systému Windows s odpovídající jazyková sada nainstalovaná nebo správně lokalizovanou verzi Windows.

## <a name="fully-supported-features"></a>Plně podporované funkce

V době návrhu v sadě Visual Studio můžete použít obousměrné jazyky při zadávání textu, vytváření názvů objektů a při ukládání a otevírání souborů.

### <a name="text-entry"></a>Zadání textu

Visual Studio podporuje kódování Unicode, takže když systém je nastaven na odpovídající národní prostředí a jazyk, můžete zadat text ve arabské nebo hebrejské. (Arabské podpora zahrnuje kašidy a diakritických znamének.)

### <a name="arabic-or-hebrew-object-names"></a>Arabský nebo hebrejský názvy objektů

Obousměrné jazyky můžete přiřadit názvy řešení, projekty, soubory, složky a tak dále. V kódu můžete použít obousměrné jazyky pro názvy proměnných, tříd, objektů, atributy, metadata a další prvky. Při práci s arabština, můžete použít libovolný Arabské znaků včetně kašidy a diakritických znamének.

Tyto prvky můžete být pojmenované pomocí arabské nebo hebrejské a jsou správně zpracovány pomocí sady Visual Studio:

- Řešení, projektů a názvy souborů, včetně některou ze složek, které jsou v cestě projektu.

   **Průzkumník řešení** správně zobrazuje řešení a názvy elementů.

- Obsah souboru.

   Můžete otevřít nebo uložit soubory s kódováním Unicode nebo s vybranou znakovou stránkou.

- Datové prvky.

   **Průzkumník serveru** správně zobrazuje tyto prvky a můžete je upravit.

- Prvky zkopírováno do schránky Windows.

- Atributy a metadata.

- Hodnoty vlastností.

   Arabský nebo hebrejský text v můžete použít **vlastnosti** okna. V okně umožňuje přepínat mezi pořadí čtení zprava doleva a doprava a doleva pomocí standardních klávesových úhozů Windows (**Ctrl**+**RightShift** zprava doleva a **Ctrl**+**LeftShift** pro zleva doprava).

- Kód a text literálu.

   V editoru kódu vám pomůže arabské nebo hebrejské název třídy, funkce, proměnné, vlastnosti, řetězcové literály, atributy a tak dále. Editor ale nepodporuje pořadí čtení zprava doleva. text vždy začíná na levém okraji.

   > [!TIP]
   > Byste měli umístit řetězcové literály do souborů prostředků místo pevného kódování je do vašich aplikací. Další informace najdete v tématu [prostředky v aplikacích klasické pracovní plochy (.NET Framework)](/dotnet/framework/resources/index).

   > [!NOTE]
   > Musíte být konzistentní vzhledem k aplikacím v jak odkazovat na objekty s názvem v arabština a hebrejština. Například pokud používáte kašidy názvů Arabské proměnné, musíte vždycky použít kašida k odkazování na, že bude výsledek proměnné nebo chyby.

- Komentáře ke kódu. Vytvoření komentářů v arabské nebo hebrejské. Můžete také těchto jazyků v nástroji Tvůrce komentář.

### <a name="file-encoding"></a>Kódování souboru

Můžete uložit a otevírání souborů se konkrétní jazyk nebo kódování Unicode. Další informace najdete v tématu [jak: Ukládání a otevírání souborů s kódováním](../ide/how-to-save-and-open-files-with-encoding.md).

## <a name="right-to-left-reading-order"></a>Pořadí čtení zprava doleva

Visual Studio má omezenou podporu pro pořadí čtení zprava doleva. Ve výchozím nastavení použijte ovládací prvky textového vstupu v sadě Visual Studio pořadí čtení zleva doprava. Ve většině případů můžete použít standardní Windows gesta přepnout pořadí čtení. Například můžete stisknout **Ctrl**+**RightShift** přepnout **vlastnosti** okna pro podporu hodnoty vlastností pořadí čtení zprava doleva.

Pořadí čtení zprava doleva není podporován v sadě Visual Studio na těchto místech:

- Zaškrtávací políčka, rozevírací seznamy a další ovládací prvky v dialogových oknech sady Visual Studio použijte vždy pořadí čtení zleva doprava.

- Editor kódu (a textový editor) nepodporuje pořadí čtení zprava doleva. Můžete zadat text v jazyce obousměrný, ale je vždy o pořadí čtení zleva doprava.

## <a name="see-also"></a>Viz také:

- [Vývoj globalizovaných a lokalizovaných aplikací](globalizing-and-localizing-applications.md)
