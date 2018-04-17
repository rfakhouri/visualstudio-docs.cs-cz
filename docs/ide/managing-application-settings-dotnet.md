---
title: Správa nastavení aplikace (.NET) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- msvse_settingsdesigner.err.nameblank
helpviewer_keywords:
- application settings [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe0daf11aa2cb6b8eb4d0e07bfd079f531831f29
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="managing-application-settings-net"></a>Správa nastavení aplikace (.NET)

Nastavení aplikace umožňují ukládat informace o aplikaci dynamicky. Nastavení Povolit ukládání informací v klientském počítači, který by neměly být obsažené v kódu aplikace (například připojovací řetězec), uživatelských předvoleb a další informace, které potřebujete za běhu.

Nastavení aplikace nahradit dynamické vlastnosti používané v dřívějších verzích sady Visual Studio.

Každé nastavení aplikace musí mít jedinečný název. Název může být libovolnou kombinací písmena, číslice nebo podtržítko nezačíná číslo a nesmí obsahovat mezery. Název můžete změnit prostřednictvím `Name` vlastnost.

Nastavení aplikace mohou být uloženy jako libovolný typ dat, který může být serializován do formátu XML nebo má `TypeConverter` , která implementuje `ToString` / `FromString`. Nejběžnější typy jsou `String`, `Integer`, a `Boolean`, ale také můžete uložit hodnoty jako <xref:System.Drawing.Color>, <xref:System.Object>, nebo jako připojovací řetězec.

Nastavení aplikace také obsahuje hodnotu. Hodnota nastavená **hodnotu** vlastnosti a musí odpovídat datovému typu nastavení.

Kromě toho nastavení aplikace mohou být vázány na vlastnost formuláře nebo ovládacího prvku v době návrhu.

Existují dva typy nastavení aplikace založené na rozsahu:

- Nastavení rozsahu aplikace lze použít pro informace, jako je adresa URL pro webovou službu nebo připojovací řetězec databáze. Tyto hodnoty jsou přidružené k aplikaci. Proto uživatelé je nelze změnit za běhu.

- Nastavení rozsahu uživatele můžete použít informace, jako je například uchování poslední pozice formuláře nebo předvoleb písma. Uživatelé můžou tyto hodnoty změnit za běhu.

Typ nastavení můžete změnit pomocí **oboru** vlastnost.

Systém projektu ukládá nastavení aplikace v dva soubory XML:

- soubor app.config, který je vytvořen v době návrhu při vytváření první nastavení aplikace

- user.config soubor, který je vytvořen v době běhu, když uživatel, který spouští aplikaci změní hodnotu jakékoli uživatelské nastavení.

Všimněte si, že změny v nastavení uživatelského nezapisují na disk, pokud aplikace konkrétně volá metodu k tomu.

## <a name="creating-application-settings-at-design-time"></a>Vytvoření nastavení aplikace v době návrhu

V době návrhu, můžete vytvořit dvěma způsoby nastavení aplikace: pomocí **nastavení** stránky **Návrhář projektu**, nebo pomocí **vlastnosti** okna pro formuláře nebo řízení, které umožňuje svázat nastavení vlastnosti.

Když vytvoříte nastavení rozsahu aplikace (například připojovací řetězec databáze nebo odkaz na prostředky serveru), [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uloží do app.config se `<applicationSettings>` značky. (Připojovací řetězce jsou uloženy v části `<connectionStrings>` značky.)

Při vytváření uživatelských nastavení (například výchozí písmo, domovskou stránku nebo velikost okna), [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uloží do app.config se `<userSettings>` značky.

> [!IMPORTANT]
> Pokud ukládáte připojovací řetězce v souboru app.config, byste měli vzít opatření, aby se zabránilo odhalení citlivých informací, třeba hesla nebo cesty serveru v připojovacím řetězci.
>
> Pokud pořídíte informace o připojovacím řetězci z externího zdroje, například uživatelské zadání ID uživatele a heslo, musíte být opatrní, abyste ověřili, že hodnoty, které můžete použít k vytvoření připojení k řetězec neobsahují další parametry připojovacího řetězce který změnit chování připojení.
>
> Zvažte použití funkce chráněné konfigurace pro šifrování citlivých informací v konfiguračním souboru. V tématu [chrání informace o připojení](/dotnet/framework/data/adonet/protecting-connection-information) Další informace.

> [!NOTE]
> Protože neexistuje žádný model konfiguračního souboru pro knihovny tříd, nastavení aplikace nelze použít u projektů knihovny tříd. Výjimkou je Visual Studio Tools for Office DLL projektu, který může mít konfigurační soubor.

## <a name="using-customized-settings-files"></a>Použití vlastních souborů nastavení

Do projektu za vhodné řízení skupiny nastavení, můžete přidat vlastní soubory nastavení. Nastavení, které jsou obsaženy v jednom souboru jsou načtena a uloženy jako celek. Proto možnost Uložit nastavení v samostatné soubory pro často používané a zřídka používané skupiny můžete ušetřit čas načítání a ukládá se nastavení.

Můžete například přidat soubor jako je SpecialSettings.settings do projektu. Během vaší `SpecialSettings` třída není vystavený v `My` obor názvů, **kód zobrazení** může číst soubor vlastní nastavení, která obsahuje `Partial Class SpecialSettings`.

Návrhář nastavení nejprve hledá soubor Settings.settings, který vytvoří systém projektu; Toto je výchozí soubor, který se zobrazí v Návrháři projektu **nastavení** kartě. Settings.Settings je umístěn ve složce My projektu pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty a ve složce vlastnosti [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekty. Návrhář projektu pak hledá další nastavení soubory v kořenové složce projektu. Proto byste měli existuje umístit soubor s vlastním nastavením. Pokud přidáte do projektu soubor .settings jinde, Návrhář projektu nebude možné najít.

## <a name="accessing-or-changing-application-settings-at-run-time-in-visual-basic"></a>Přístup nebo změna nastavení aplikace za běhu v jazyce Visual Basic

V projekty Visual Basic, můžete přístup k nastavení aplikace v době běhu pomocí `My.Settings` objektu. Na **nastavení** klikněte na tlačítko **zobrazit kód** tlačítko Zobrazit soubor Settings.vb. Definuje Settings.vb `Settings` třídy, která umožňuje zpracování těchto událostí na třídě nastavení: <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>, <xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>, <xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>, a <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>. Všimněte si, že `Settings` třída v Settings.vb je částečné třídu, která se zobrazí pouze uživatele kód, ne celý vygenerované třídy. Další informace o přístup k nastavení aplikace pomocí `My.Settings` objektu, najdete v části [přístup k nastavení aplikace (rozhraní .NET Framework)](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings).

Hodnoty nastavení rozsahu uživatele, které uživatel změní za běhu (například pozici formuláře) jsou uloženy v souboru user.config. Všimněte si, že výchozí hodnoty jsou stále uloženy v souboru app.config.

Pokud jste změnili uživatelských nastavení při běhu, například v aplikaci, testování a chcete resetovat na výchozí hodnoty těchto nastavení, klikněte na **synchronizovat** tlačítko.

Důrazně doporučujeme použít `My.Settings` objekt a výchozí soubor .settings k nastavení přístupu. Je to proto, že použijete návrháře nastavení k přiřazení vlastnosti k nastavení a kromě toho se automaticky uloží nastavení uživatele před ukončení aplikace. Ale aplikace Visual Basic nastavení můžete přejít přímo. V takovém případě budete muset přístup `MySettings` třídy a použít vlastní soubor .settings v kořenovém adresáři projektu. Musíte také uložit nastavení uživatele před ukončením aplikace, jako byste to udělali pro C# aplikaci; je to popsané v následující části.

## <a name="accessing-or-changing-application-settings-at-run-time-in-c"></a>Přístup nebo změna nastavení aplikace za běhu v jazyce C# #

V jiných jazycích, než jazyka Visual Basic, například C#, je nutné přejít `Settings` třídy přímo, jak je znázorněno v následujícím [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] příklad.

```csharp
Properties.Settings.Default.FirstUserSetting = "abc";
```

Musíte také explicitně volat `Save` metoda této obálkové třídy, aby zachovaly uživatelská nastavení. Obvykle k tomu `Closing` obslužné rutiny události hlavního formuláře. Následující příklad jazyka C# ukazuje volání `Save` metoda.

```csharp
Properties.Settings.Default.Save();
```

Obecné informace o přístup k nastavení aplikace pomocí `Settings` třídy najdete v tématu [přehled nastavení aplikace (rozhraní .NET Framework)](/dotnet/framework/winforms/advanced/application-settings-overview). Informace o iterace v rámci nastavení najdete v tématu to [příspěvek na fóru](http://social.msdn.microsoft.com/Forums/vstudio/40fbb470-f1e8-4a02-a4a0-9f62b54d0fc4/is-this-possible-propertiessettingsdefault?forum=csharpgeneral).

## <a name="see-also"></a>Viz také

[Přístup k nastavení aplikace (rozhraní .NET Framework)](/dotnet/visual-basic/developing-apps/programming/app-settings/accessing-application-settings)
