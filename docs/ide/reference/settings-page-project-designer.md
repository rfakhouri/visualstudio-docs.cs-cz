---
title: Stránka nastavení, Návrhář projektu
ms.date: 06/14/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- ApplicationSettingsOverview
helpviewer_keywords:
- Settings page in Project Designer
- Project Designer, Settings page
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c0f7b47b56522f5c4aeef0054e6b7b52434ff87
ms.sourcegitcommit: 562867be91ee1aebbed4658c8de0949f422860fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/14/2018
ms.locfileid: "35608944"
---
# <a name="settings-page-project-designer"></a>Stránka nastavení, Návrhář projektu

Použití **nastavení** stránky v Návrháři projektu k nastavení aplikace projektu. Nastavení aplikace umožňují uložení a načtení nastavení vlastností a další informace pro vaši aplikaci dynamicky. Umožňují také udržovat vlastní aplikaci a uživatelské předvolby v klientském počítači. Další informace najdete v tématu [Správa nastavení aplikace](../managing-application-settings-dotnet.md).

Pro přístup k **nastavení** vyberte uzel projektu v **Průzkumníku řešení**a potom vyberte **projektu** > **vlastnosti**. Jakmile se zobrazí v Návrháři projektu, vyberte **nastavení** kartě.

## <a name="header-bar"></a>Záhlaví panelu

Na panelu hlavičky v horní části **nastavení** stránka obsahuje několik ovládacích prvků:

**Synchronizovat**

**Synchronizovat** obnoví nastavení rozsahu uživatele, které aplikace používá za běhu nebo během ladění na výchozí hodnoty, jak jsou definovány v době návrhu. Chcete obnovit data, odeberte běhu generované soubory specifické pro aplikaci z disku, nikoli z projektu data.

**Nastavení webové zatížení**

**Načtení nastavení webové** zobrazí **přihlášení** dialogu, který umožňuje načíst nastavení pro ověřeného uživatele nebo pro anonymní uživatele. Toto tlačítko je povolené jenom v případě, že jste povolili klientské aplikační služby na **služby** stránky a zadán **nastavení webové služby umístění**.

**Zobrazení kódu**

Pro projekty C# **kód zobrazení** tlačítka můžete zobrazit kód *Settings.cs* souboru. Definuje tento soubor `Settings` třídy, která umožňuje zpracovávat na konkrétní události `Settings` objektu. V jiných jazyků než jazyka Visual Basic, musíte explicitně zavolat `Save` metoda této obálkové třídy, aby zachovaly uživatelská nastavení. Obvykle k tomu **zavření** obslužné rutiny události hlavního formuláře. Tady je příklad volání `Save` metoda:

```csharp
Properties.Settings.Default.Save();
```

Pro projekty Visual Basic **kód zobrazení** tlačítka můžete zobrazit kód *Settings.vb* souboru. Definuje tento soubor `MySettings` třídy, která umožňuje zpracovávat na konkrétní události `My.Settings` objektu. Další informace o přístup k nastavení aplikace pomocí `My.Settings` objektu, najdete v části [přístup k nastavení aplikace](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings).

Další informace o přístup k nastavení aplikace najdete v tématu [nastavení aplikace pro Windows Forms](/dotnet/framework/winforms/advanced/application-settings-for-windows-forms).

**Modifikátor přístupu**

**– Modifikátor přístupu** tlačítko určuje úroveň přístupu `Properties.Settings` (v jazyku C#) nebo `My.Settings` (v jazyce Visual Basic) pomocná třída, která je Visual Studio vytvoří v *Settings.Designer.cs* nebo *Settings.Designer.vb*.

Pro projekty Visual C#, může být – modifikátor přístupu **interní** nebo **veřejné**.

Pro projekty Visual Basic, může být – modifikátor přístupu **Friend** nebo **veřejné**.

Ve výchozím nastavení je **interní** v jazyce C# a **Friend** v jazyce Visual Basic. Když Visual Studio generuje pomocné třídy jako **interní** nebo **Friend**, spustitelný soubor (*.exe*) aplikace nemají přístup k prostředkům a nastavení, které jste přidali do služby třídy knihovny (*.dll* soubory). Pokud máte sdílet prostředky a nastavení z knihovny tříd, nastavit – modifikátor přístupu **veřejné**.

Další informace o nastavení pomocných tříd, najdete v části [Správa nastavení aplikace](../managing-application-settings-dotnet.md).

## <a name="settings-grid"></a>Nastavení mřížky

**Nastavení mřížky** slouží ke konfiguraci nastavení aplikace. Tato mřížka obsahuje následující sloupce:

**Jméno**

Zadejte název pro nastavení aplikace v tomto poli.

**Typ**

Pomocí rozevíracího seznamu vyberte typ nastavení. Nejčastěji používané typy v seznamu se zobrazí rozevírací seznam, například **řetězec**, **(připojovací řetězec)**, a **System.Drawing.Font**. Můžete si zvolit jiný typ výběrem **Procházet** na konci tohoto seznamu a pak vybrat typ z **vyberte typ** dialogové okno. Po zvolení typu, se přidá do běžné typy v rozevíracím seznamu (pro pouze aktuálním řešení).

**Rozsah**

Vyberte buď **aplikace** nebo **uživatele**.

Nastavení rozsahu aplikace, jako je například připojovací řetězce jsou přidružené k aplikaci. Uživatelé nemohou měnit nastavení rozsahu aplikace za běhu.

Uživatelských nastavení, jako je například systém písem a jsou určena pro použití pro uživatelské předvolby. Uživatelé mohou změnit je za běhu.

**Hodnota**

Data nebo hodnota přidružený k nastavení aplikace. Například pokud je nastavení písmo, jeho hodnota může být **Verdana, 9.75pt, styl = Bold**.

## <a name="see-also"></a>Viz také:

- [Správa nastavení aplikace](../managing-application-settings-dotnet.md)
- [Přístup k nastavení aplikace (Visual Basic)](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings)