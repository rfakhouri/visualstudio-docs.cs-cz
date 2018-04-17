---
title: 'Postupy: zpětné transformace rozšíření pro Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 06/25/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 2d6cf53c-011e-4c9e-9935-417edca8c486
author: willbrown
ms.author: willbrown
manager: justinclareburt
ms.workload:
- willbrown
ms.openlocfilehash: 9d8d0dc2e5c8c95b5f2502ef5a48e6f97c26e289
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-make-extensions-compatible-with-visual-studio-2017-and-visual-studio-2015"></a>Postupy: Zkontrolujte rozšíření kompatibilní s Visual Studio 2017 a Visual Studio 2015

Tento dokument vysvětluje, jak zajistit odezvy mezi Visual Studio 2015 a Visual Studio 2017 rozšiřitelnost projektů. Po dokončení tohoto upgradu, bude moct otevírat, sestavení, nainstalovat a spustit v sadě Visual Studio 2015 a Visual Studio 2017 projektu.  Jako odkaz, některá rozšíření, které můžou mít odezvu mezi Visual Studio 2015 a Visual Studio 2017 naleznete [sem](https://github.com/Microsoft/VSSDK-Extensibility-Samples) v příkladech rozšiřitelnost společnosti Microsoft.

Pokud jenom chcete vytvořit ve Visual Studio 2017, ale má výstup VSIX spouštění v sadě Visual Studio 2015 a Visual Studio 2017, potom se podívejte [dokumentu migrace rozšíření](how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

>**Poznámka:** z důvodu změn v sadě Visual Studio mezi verzemi, některé věci, které fungovaly v jedné verzi nebude fungovat jiné. Zajistit, aby funkce se pokoušíte získat přístup, jsou dostupné v obou verzích, a rozšíření budou mít neočekávané výsledky.

Tady je přehled kroků, které budete v tomto dokumentu k odezvě VSIX dokončení:

1. Importujte správné balíčky NuGet.
2. Aktualizujte Manifest rozšíření:
    * Cíl instalace
    * Požadavky
3. Aktualizace CSProj:
    * Aktualizace `<MinimumVisualStudioVersion>`.
    * Přidat `<VsixType>` vlastnost.
    * Přidat vlastnost ladění `($DevEnvDir)` 3krát.
    * Přidání podmínek pro import nástroje pro sestavení a cíle.

4. Sestavení a testů

## <a name="environment-setup"></a>Nastavení prostředí

Tento dokument předpokládá, že máte nainstalovaný na počítači následující:

* Visual Studio 2015 se VS SDK nainstalován
* Visual Studio 2017 se zatížením rozšiřitelnost nainstalován

## <a name="recommended-approach"></a>Doporučeným přístupem

Důrazně doporučujeme spustit tento upgrade pomocí sady Visual Studio 2015, místo Visual Studio 2017. Hlavní výhodou vývoj v sadě Visual Studio 2015 je zajistit, že není referenční sestavení, které nejsou k dispozici v sadě Visual Studio 2015. Pokud uděláte vývoj v aplikaci Visual Studio 2017, existuje riziko, že může způsobit závislý na sestavení, které existuje pouze v Visual Studio 2017.

## <a name="ensure-there-is-no-reference-to-projectjson"></a>Ujistěte se, že neexistuje žádný odkaz do souboru project.json

Později v tomto dokumentu jsme vloží podmíněného import příkazy v souboru *.csproj.  Pokud vaše NuGet odkazy jsou uložené v souboru project.json to nebude fungovat. Jako takový doporučujeme přesunout všechny NuGet odkazy na soubor packages.config.
Pokud projekt obsahuje soubor project.json:

* Povšimněte si odkazy v souboru project.json.
* V Průzkumníku řešení odstraňte soubor project.json z projektu.
    * Tato akce odstraní soubor project.json a jeho odebrání z projektu.
* Přidání že odkazů NuGet zpátky do projektu.
    * Klikněte pravým tlačítkem na řešení a zvolte **spravovat balíčky NuGet pro řešení...**
    * Visual Studio pro vás automaticky vytvoří soubor packages.config

>**Poznámka:** Pokud projekt obsahoval EnvDTE balíčky, se může třeba přidat kliknutím pravým tlačítkem na **odkazy** výběr **přidat odkaz** a přidání odpovídající odkaz.  Pomocí balíčků NuGet může vytvořit chyby při pokusu o sestavení projektu.

## <a name="adding-appropriate-build-tools"></a>Nástroje pro přidání odpovídající sestavení

Aby byly musíme přidat nástroje sestavení, které vám umožní nám vytvářet a ladit správně. Společnost Microsoft vytvořila sestavení pro toto názvem Microsoft.VisualStudio.Sdk.BuildTasks.

K vytváření a nasazování VSIXv3 v sadě Visual Studio 2015 a 2017, budete potřebovat následující balíčky NuGet:

Version | Integrované nástroje
--- | ---
Visual Studio 2015 | Microsoft.VisualStudio.Sdk.BuildTasks.14.0
Visual Studio 2017 | Microsoft.VSSDK.BuildTool

Postupujte následovně:

* Do projektu přidejte balíček NuGet Microsoft.VisualStudio.Sdk.BuildTasks.14.0.
* Pokud váš projekt Microsoft.VSSDK.BuildTools neobsahuje, přidejte ji.
* Zkontrolujte verzi Microsoft.VSSDK.BuildTools 15.x nebo vyšší.

## <a name="update-extension-manifest"></a>Aktualizujte Manifest rozšíření

### <a name="1-installation-targets"></a>1. Instalace cíle

Potřebujeme říct sadě Visual Studio, jaké verze cíle pro vytváření VSIX.  Tyto odkazy jsou obvykle buď do verze 14.0 (Visual Studio 2015) nebo 15.0 (Visual Studio 2017).  V našem případě chceme sestavení VSIX, který bude instalovat rozšíření pro obě, takže potřebujeme mít obě verze.  Pokud chcete, aby vaše VSIX pro sestavení a nainstalovat ve verzích starších než 14.0, to můžete provést nastavením číslo starší verze; ale 10.0 a starší verze již nejsou podporovány.

* Otevřete soubor source.extension.vsixmanifest v sadě Visual Studio.
* Otevřete **nainstalovat cíle** kartě.
* Změna **rozsahu verze** k [14,0, 16,0).  ' [' Informuje zahrnují verze 14,0 a všechny po jeho sady Visual Studio.  Tím ')' informuje zahrnují všechny verze 15.0 až do, s výjimkou 16.0 verze sady Visual Studio.
* Všechny změny uložte a zavřete všechny instance sady Visual Studio.

![Obrázek instalace služby cíle](media/visual-studio-installation-targets-example.png)

### <a name="2-adding-prerequisites-to-the-extensionvsixmanifest-file"></a>2. Přidání požadavky na soubor extension.vsixmanifest

Požadavky jsou nová funkce s Visual Studio 2017.  V takovém případě potřebujeme editoru Visual Studio základní předpokladem je. Vzhledem k tomu, že aplikace Visual Studio 2015 VSIX návrháře nezpracovává nové `Prerequisites` části, budete muset upravit tuto část ručně v kódu XML.  Alternativně můžete otevřít Visual Studio 2017 a použít aktualizované návrháře manifestu vložit požadavky.

K tomu ručně:

* Přejděte do adresáře projektu v Průzkumníku souborů.
* Otevřete `extension.vsixmanifest` soubor v textovém editoru.
* Přidejte následující značku:

```xml
<Prerequisites>
    <Prerequisite Id="Microsoft.VisualStudio.Component.CoreEditor" Version="[15.0,16.0)" DisplayName="Visual Studio core editor" />
</Prerequisites>
```

* Soubor uložte a zavřete.

>**Poznámka:** Pokud zvolíte možnost dosáhnout pomocí návrháře VSIX v Visual Studio 2017, budete muset ručně upravit požadovaných verze zajistit je kompatibilní se všemi verzemi Visual Studio 2017.  To je proto návrháře bude vložit minimální verze vaší aktuální verzí sady Visual Studio (například 15.0.26208.0).  Ale vzhledem k tomu, že jiní uživatelé mohou mít starší verze, můžete ručně upravit, pokud to chcete 15.0.

V tomto okamžiku souboru manifestu by měl vypadat přibližně takto:

![Příklad požadavky](media/visual-studio-prerequisites-example.png)

## <a name="modify-the-project-file-myprojectcsproj"></a>Upravte soubor projektu (myproject.csproj)

Důrazně doporučujeme mít odkaz na upravené .csproj otevřete přitom tento krok.  Můžete najít několik příkladů [zde](https://github.com/Microsoft/VSSDK-Extensibility-Samples).  Vyberte všechny ukázkové rozšiřitelnost, najít soubor .csproj pro referenci a provést následující kroky:

* Přejděte do adresáře projektu v Průzkumníku souborů.
* Pomocí textového editoru otevřete soubor myproject.csproj.

### <a name="1-update-the-minimumvisualstudioversion"></a>1. Aktualizace MinimumVisualStudioVersion

* Nastavte minimální sady visual studio verzi `$(VisualStudioVersion)` a přidejte příkaz, podmíněného pro ni.  Pokud neexistují, přidejte tyto značky.  Ujistěte se, že zadané značky jsou nastavené jako níže:

```xml
<VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">14.0</VisualStudioVersion>
<MinimumVisualStudioVersion>$(VisualStudioVersion)</MinimumVisualStudioVersion>
```

### <a name="2-add-the-vsixtype-property"></a>2. Přidat vlastnost VsixType

* Přidejte následující značku `<VsixType>v3</VsixType>` do skupiny vlastnost.

>**Poznámka:** se doporučuje to přidat dole `<OutputType></OutputType>` značky.

### <a name="3-add-the-debugging-properties"></a>3. Přidejte ladění vlastnosti

* Přidejte následující skupiny vlastností:

```xml
<PropertyGroup>
    <StartAction>Program</StartAction>
    <StartPrograms>$(DevEnvDir)devenv.exe</StartPrograms>
    <StartArguments>/rootsuffix Exp</StartArguments>
</PropertyGroup>
```

* Odstranit všechny instance následující ze souboru .csproj a všechny. csproj.user soubory:

```xml
<StartAction>Program</StartAction>
<StartPrograms>$(ProgramFiles)\Microsoft Visual Studio 14.0\Common7\IDE\devenv.exe</StartPrograms>
<StartArguments>/rootsuffix Exp</StartArguments>
```

### <a name="4-add-conditions-to-the-build-tools-imports"></a>4. Přidání podmínek do importy nástroje pro sestavení

* Přidat další podmíněné příkazy k `<import>` značky, které mají Microsoft.VSSDK.BuildTools odkaz.  To provedete vkládání `'$(VisualStudioVersion)' != '14.0' And` vpředu příkaz podmínky.  Tyto příkazy se zobrazí v záhlaví a zápatí csproj souboru.

Příklad:

```xml
<Import Project="packages\Microsoft.VSSDK.BuildTools.15.0.26201…" Condition="'$(VisualStudioVersion)' != '14.0' And Exists(…" />
```

* Přidat další podmíněné příkazy k `<import>` značky, které mají Microsoft.VisualStudio.Sdk.BuildTasks.14.0.  To provedete vkládání `'$(VisualStudioVersion)' == '14.0' And` vpředu příkaz podmínky. Tyto příkazy se zobrazí v záhlaví a zápatí csproj souboru.

Příklad:

```xml
<Import Project="packages\Microsoft.VisualStudio.Sdk.BuildTasks.14.0.14.0…" Condition="'$(VisualStudioVersion)' == '14.0' And Exists(…" />
```

* Přidat další podmíněné příkazy k `<Error>` značky, které mají Microsoft.VSSDK.BuildTools odkaz.  To provedete vkládání `'$(VisualStudioVersion)' != '14.0' And` vpředu příkaz podmínky. Tyto příkazy se zobrazí v zápatí csproj souboru.

Příklad:

```xml
<Error Condition="'$(VisualStudioVersion)' != '14.0' And Exists('packages\Microsoft.VSSDK.BuildTools.15.0.26201…" />
```

* Přidat další podmíněné příkazy k `<Error>` značky, které mají Microsoft.VisualStudio.Sdk.BuildTasks.14.0.  To provedete vkládání `'$(VisualStudioVersion)' == '14.0' And` vpředu příkaz podmínky. Tyto příkazy se zobrazí v zápatí csproj souboru.

Příklad:

```xml
<Error Condition="'$(VisualStudioVersion)' == '14.0' And Exists('packages\Microsoft.VisualStudio.Sdk.BuildTasks.14.0.14.0…" />
```

* Csproj soubor uložte a zavřete ho.

## <a name="test-the-extension-installs-in-visual-studio-2015-and-visual-studio-2017"></a>Testování instalace rozšíření v sadě Visual Studio 2015 a Visual Studio 2017

Projekt v tomto okamžiku by měli být připravení sestavení VSIXv3, které můžete nainstalovat na Visual Studio 2015 a Visual Studio 2017.

* Otevřete projekt v sadě Visual Studio 2015
* Sestavení projektu a potvrďte ve výstupu, který sestaví VSIX správně
* Přejděte do adresáře projektu
* Otevřete přihrádky -> složky ladění
* Dvakrát klikněte na soubor VSIX a instalaci rozšíření v sadě Visual Studio 2015 a Visual Studio 2017
* Zkontrolujte, zda se zobrazí v nástrojích pro rozšíření -> rozšíření a aktualizace v části "Nainstalovaná".
* Pokus o spuštění nebo použití rozšíření zkontrolujte, že funguje

![Hledání VSIX](media/finding-a-VSIX-example.png)

>**Poznámka:** Pokud projekt přestane reagovat s zpráva force "otevření souboru" vypnout Visual Studio, přejděte do adresáře projektu, zobrazit skrytých složek a odstranit neodstraňujte složku.
