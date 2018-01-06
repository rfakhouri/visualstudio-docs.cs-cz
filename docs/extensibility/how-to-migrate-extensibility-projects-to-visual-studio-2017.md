---
title: "Postupy: migrace rozšiřitelnost projektů na Visual Studio 2017 | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ca07b00-a3ff-40ab-b647-c0a93b55e86a
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8d49ff89f38b0279c60f49ee7d5856d21fd5fc4a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-migrate-extensibility-projects-to-visual-studio-2017"></a>Postupy: migrace rozšiřitelnost projektů na Visual Studio 2017

Tento dokument vysvětluje postup upgradu rozšiřitelnost projektů na Visual Studio 2017. Kromě popisující, jak aktualizovat soubory projektu, se také popisuje, jak upgradovat z verze rozšíření manifestu 2 (VSIX v2) na nové verze 3 VSIX manifestu formát (VSIX v3).

## <a name="install-visual-studio-2017-with-required-workloads"></a>Nainstalovat Visual Studio 2017 s požadované úlohy

Zajistěte, aby že vaše instalace zahrnuje následující úlohy:

* Vývoj aplikací rozhraní .NET
* Vývoj rozšíření pro Visual Studio

## <a name="open-vsix-solution-in-visual-studio-2017"></a>Otevřete řešení VSIX v Visual Studio 2017

Všechny projekty VSIX bude vyžadovat jednosměrný upgradu hlavní verze pro Visual Studio 2017.

Soubor projektu (například *.csproj) bude možné aktualizovat:

* MinimumVisualStudioVersion - teď nastavená na 15.0
* OldToolsVersion (pokud existuje dříve)-teď nastavená na 14.0

## <a name="update-the-microsoftvssdkbuildtools-nuget-package"></a>Balíček Microsoft.VSSDK.BuildTools NuGet aktualizace

>**Poznámka:** Pokud vaše řešení neodkazuje na balíček Microsoft.VSSDK.BuildTools NuGet, můžete tento krok přeskočit.

K sestavení rozšíření v nové v3 VSIX formátu (verze 3), vaše řešení se musela být vytvořená s nástroji pro nové sestavení VSSDK. To bude nainstalován s Visual Studio 2017, ale může být rozšíření v2 VSIX podržíte odkaz na starší verzi prostřednictvím balíčku NuGet. Pokud ano, musíte ručně nainstalovat aktualizaci balíčku Microsoft.VSSDK.BuildTools NuGet pro vaše řešení.

Aktualizace NuGet odkazy na Microsoft.VSSDK.BuildTools:

* Klikněte pravým tlačítkem na řešení a zvolte **spravovat balíčky NuGet pro řešení...**
* Přejděte na **aktualizace** kartě.
* Vyberte Microsoft.VSSDK.BuildTools (nejnovější verze).
* Stiskněte klávesu **aktualizace**.

![VSSDK sestavovací nástroje](media/vssdk-build-tools.png)

## <a name="make-changes-to-the-vsix-extension-manifest"></a>Proveďte změny manifest rozšíření VSIX

Zajistěte, aby uživatele instalace sady Visual Studio byla všechna sestavení, které jsou nutné ke spuštění rozšíření, zadejte všechny požadované součásti nebo balíčky v souboru manifestu rozšíření. Když se uživatel pokusí nainstalovat rozšíření, VSIXInstaller zkontroluje, zda jsou nainstalovány všechny požadované součásti. Pokud chybí některé, uživatel se vyzve k instalaci chybějících součástí jako součást procesu instalace rozšíření.

>**Poznámka:** minimálně všechna rozšíření zadejte součást Visual Studio základních editor požadovanou součástí.

* Upravte soubor manifestu rozšíření (obvykle nazvaný source.extension.vsixmanifest).
* Ujistěte se, `InstallationTarget` zahrnuje 15.0.
* Přidejte požadované instalační požadavky (jak je znázorněno v následujícím příkladu).
  * Doporučujeme, že zadejte pouze ID součástí pro požadavky na instalaci.
  * Najdete v části na konci tohoto dokumentu pro [pokyny k identifikaci ID součástí](#finding-component-ids).

Příklad:

```xml
<PackageManifest>
 ...
    <Prerequisites>
        <Prerequisite Id="Microsoft.VisualStudio.Component.CoreEditor" Version="[15.0,16.0)" />
        <Prerequisite Id="Microsoft.VisualStudio.Component.DiagnosticTools" Version="[15.0.25814.0,16.0)" />
        <Prerequisite Id="Microsoft.VisualStudio.Shell.12.0" Version="[12.0]" />
    </Prerequisites>
 ...
</PackageManifest>
```

### <a name="option-use-the-designer-to-make-changes-to-the-vsix-extension-manifest"></a>Možnost: Změnit manifest rozšíření VSIX pomocí návrháře

Namísto provádění úprav v manifestu XML, můžete použít nové **požadavky** kartě v Návrháři Manifest vyberte požadavky a soubor XML se aktualizovat za vás.

>**Poznámka:** návrháře manifestu pouze budete moci vybrat součásti (ne úlohy nebo balíčky), které jsou nainstalované na aktuální instanci aplikace Visual Studio. Pokud potřebujete přidat předpokladem pro úlohy, balíčku nebo součásti, která není momentálně nainstalována, upravte přímo do manifestu XML.

* Otevřete soubor source.extension.vsixmanifest [návrhu].
* Vyberte **požadavky** kartě a stiskněte klávesu **nový** tlačítko.

  ![Návrhář manifestu VSIX](media/vsix-manifest-designer.png)

* **Přidat nové požadovaných** otevře se okno.

  ![přidání požadovaných součástí vsix](media/add-vsix-prerequisite.png)

* Klikněte na rozevírací seznam pro **název** a vyberte požadované předpokladů.
* V případě potřeby aktualizaci verze.

  >Poznámka: Pole verze bude předem vyplněny verzi aktuálně nainstalovanou součástí, rozsah pokrývání až (s výjimkou) další hlavní verze součásti.

  ![přidání požadovaných součástí roslyn](media/add-roslyn-prerequisite.png)

* Press **OK**.

## <a name="update-debug-settings-for-project"></a>Aktualizovat nastavení pro ladění pro projekt

Pokud chcete ladit rozšíření v experimentální instanci sady Visual Studio, ujistěte se, že nastavení projektu pro **ladění** > **zahájení** má **spustit externí program:** hodnota nastavena na soubor devenv.exe instalace sady Visual Studio 2017.

Může vypadat:

```
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\devenv.exe
```

![spuštění externího programu](media/start-external-program.png)

>**Poznámka:** ladění spustit akci je obvykle uložen ve. csproj.user souboru. Tento soubor je obvykle součástí soubor .gitignore a proto se obvykle neuloží s ostatními soubory projektu, když potvrzeny do správy zdrojového kódu. Jako takový Pokud vaše řešení mít vyžádat nový od správy zdrojového kódu je pravděpodobné, že projekt bude mít žádné hodnoty nastavené pro spustit akci. Nové projekty VSIX vytvořené pomocí Visual Studio 2017 bude mít. soubor csproj.user vytvořen s výchozím nastavením odkazující k aktuálnímu adresáři instalace sady Visual Studio. Pokud provádíte migraci příponu v2 VSIX, je ale pravděpodobné,. csproj.user soubor bude obsahovat odkazy na předchozí verze sady Visual Studio Instalační adresář. Nastavení hodnoty **ladění** > **zahájení** vám umožní správné experimentální instanci sady Visual Studio spustíte při pokusu o ladění rozšíření.

## <a name="check-that-the-extension-builds-correctly-as-a-vsix-v3"></a>Zkontrolujte, že rozšíření sestavení správně (jako VSIX v3)

* Sestavení projektu VSIX.
* Rozbalte generovaného VSIX.
  * Pomocí výchozí soubor život VSIX uvnitř bin/Debug nebo Koš a verze jako VSIX [YourCustomExtension].
  * Přejmenujte VSIX .zip snadno zobrazit obsah.
* Zkontrolujte existenci tři soubory:
  * Extension.vsixmanifest
  * manifest.JSON
  * CATALOG.JSON

## <a name="check-when-all-required-prerequisites-are-installed"></a>Zkontrolujte, když jsou nainstalovány všechny požadované součásti

Test, který VSIX nainstaluje úspěšně na počítači s všechny požadované součásti nainstalovat.

>**Poznámka:** před instalací jakékoli rozšíření, ukončete všechny instance sady Visual Studio.

Pokus o instalaci rozšíření:

* Na Visual Studio 2017

![Instalační program VSIX na Visual Studio 2017](media/vsixinstaller-vs-2017.png)

* Volitelné: Zkontrolujte v dřívějších verzích sady Visual Studio.
  * Prokáže zpětné kompatibility.
  * By měla fungovat pro sadu Visual Studio 2012, Visual Studio 2013, Visual Studio 2015.
* Volitelné: Zkontrolujte, že kontrolu verze Instalační služby VSIX nabízí volba verzí.
  * Obsahuje předchozí verze sady Visual Studio (Pokud je nainstalovaná).
  * Zahrnuje Visual Studio 2017.

Pokud Visual Studio byla nedávno otevřené, může se zobrazit dialogové okno takto:

![VS spuštěných procesů](media/vs-running-processes.png)

Počkejte procesy vypnout, nebo ručně ukončení úlohy. Procesy můžete najít pomocí uvedených názvu nebo s identifikátorem PID uvedených v závorkách.

>**Poznámka:** tyto procesy nebudou vypnout automaticky a je spuštěna instance sady Visual Studio. Zkontrolujte, zda jste vypnout všechny instance sady Visual Studio na počítači - včetně těch, které od jiných uživatelů a pokoušet.

## <a name="check-when-missing-the-required-prerequisites"></a>Zaškrtněte v případě, že chybí požadované součásti

* Pokus o instalaci rozšíření na počítači s Visual Studio 2017 CONTAIN tento není nemá všechny součásti, které jsou definované v požadavky (výše).
* Zkontrolujte, zda instalace identifikuje chybějící součást/s a uvádí je jako předpoklady v VSIXInstaller.
* Poznámka: Zvýšení oprávnění se bude vyžadovat, pokud je potřeba nainstalovat s příponou všechny požadované součásti.

![Chybějící předpoklad vsixinstaller](media/vsixinstaller-missing-prerequisite.png)

## <a name="deciding-on-components"></a>Rozhodnutí týkající se součásti

Při vyhledávání vašeho závislosti, zjistíte, že může závislostí mapovat více součástí. K určení závislostí, které byste měli zadat vaše předpokladem je, doporučujeme, abyste zvolili komponenty, která má funkci podobnou rozšíření a také zvážit uživatelům a jaký typ komponenty by pravděpodobně instaloval nebo nebude na paměti, instalace. Doporučujeme také sestavování rozšíření způsobem, kde nezbytné požadavky splňují pouze minimální, který vám umožní spuštění rozšíření a další funkce, aby byly neaktivní, pokud určité součásti nezjišťují.

Chcete-li poskytnout další pokyny, myslíme, že by pár běžné typy rozšíření a jejich navrhované požadavky:

Typ rozšíření. | Zobrazovaný název | ID
--- | --- | ---
Editor | Editor základní Visual Studio  | Microsoft.VisualStudio.Component.CoreEditor
Roslyn | C# a Visual Basic | Microsoft.VisualStudio.Component.Roslyn.LanguageServices
WPF | Jádro spravované plochy pracovního vytížení | Microsoft.VisualStudio.Component.ManagedDesktop.Core
Ladicí program | Ladicí program za běhu | Microsoft.VisualStudio.Component.Debugger.JustInTime

## <a name="finding-component-ids"></a>Hledání ID součástí

Seznam součástí, které jsou seřazené podle produktu Visual Studio je v [zatížení 2017 Visual Studio a ID součástí](https://aka.ms/vs2017componentIDs). Tato součást ID používejte pro vaše požadovaných identifikátory v manifestu.

Pokud si nejste jistí, která komponenta obsahuje konkrétní binární, stažení [součást -> binární mapování tabulky](https://aka.ms/vs2017componentid-binaries).

### <a name="vs2017-componentbinarymappingxlsx"></a>vs2017 ComponentBinaryMapping.xlsx

Existují čtyři sloupce v listu aplikace Excel: **název komponenty**, **ComponentId**, **verze**, a **binární nebo názvy souborů**.  Filtry můžete použít k vyhledání a najít konkrétní součásti a binární soubory.

Pro všechny odkazy musíte nejdřív určete ty, které jsou v komponentě základní editor (Microsoft.VisualStudio.Component.CoreEditor).  Minimálně je nutné součást editor základních zadat v rámci požadavků pro všechna rozšíření. Odkazy, které jsou ponechána které nejsou v editoru jádra, přidat filtry v **binárních souborů nebo názvy souborů** vyhledejte komponenty, které žádné podmnožinu tyto odkazy.

Příklady:

* Pokud máte rozšíření ladicího programu a vědět, že váš projekt odkazuje na VSDebugEng.dll a VSDebug.dll, klikněte na tlačítko filtru v **binárních souborů nebo názvy souborů** záhlaví.  Vyhledejte "VSDebugEng.dll" a kliknutím na tlačítko OK.  Potom klikněte na tlačítko filtru v **binárních souborů nebo názvy souborů** záhlaví znovu a vyhledejte "VSDebug.dll".  Zaškrtněte políčko "Aktuální výběr pro přidat k filtrování" a kliknutím na tlačítko OK.  Teď měl vypadat **název komponenty** najít komponenty, která je většina související s vaší typ rozšíření. V tomto příkladu byste vybrali pouze v době ladicího programu a přidejte ji do vašeho vsixmanifest.
* Pokud víte, že váš projekt se zabývá elementy ladicí program, můžete hledat na "ladicí program" do vyhledávacího pole filtru na zjistit, jaké součásti obsahují ladicí program v jeho názvu.

## <a name="specifying-a-visual-studio-2017-release"></a>Určení verze Visual Studio 2017

Pokud toto rozšíření vyžaduje určitou verzi sady Visual Studio 2017, například závisí na funkci vydané v 15.3, musíte zadat číslo sestavení v vaší VSIX **InstallationTarget**. Verze 15.3 například má počet sestavení '15.0.26730.3'. Můžete zobrazit mapování k sestavení čísla verzí [zde](../install/visual-studio-build-numbers-and-release-dates.md). Použití číslo verze '15.3, nebude fungovat správně.

Pokud vaše rozšíření vyžaduje 15.3 nebo vyšší, by deklarovat **InstallationTarget verze** jako [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```