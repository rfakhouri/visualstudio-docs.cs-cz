---
title: Nasazení DSL v MSI a VSIX
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0c17ac476e0edbec73c407090cd84e6a44d9219c
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="msi-and-vsix-deployment-of-a-dsl"></a>Nasazení DSL v MSI a VSIX
Jazyk specifické pro doménu můžete nainstalovat na vašem počítači nebo na jiné počítače. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] musí být již nainstalován v cílovém počítači.

##  <a name="which"></a> Volba mezi VSIX a nasazení MSI
 Nasazení jazyka domény dvěma způsoby:

|Metoda|Výhody|
|------------|--------------|
|VSX ([!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření)|Velmi snadno nasadit: kopírování a spouštět **VSIX** souboru z DslPackage projektu.<br /><br /> Další informace najdete v části [instalace a odinstalace DSL pomocí VSX](#Installing).|
|MSI (instalačního programu soubor)|– Umožňuje uživateli otevřít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dvojitým kliknutím DSL soubor.<br />-Přidruží ikonu DSL typ souboru v cílovém počítači.<br />-Přidruží XSD (XML schema) DSL typ souboru. Tím předejdete upozornění, když soubor je načten do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].<br /><br /> Projekt instalace je nutné přidat do řešení pro vytvoření souboru MSI.<br /><br /> Další informace najdete v tématu [nasazení DSL pomocí souboru MSI](#msi).|

##  <a name="Installing"></a> Instalace a odinstalace DSL pomocí VSX
 Pokud vaše DSL je nainstalovaná touto metodou, může uživatel otevřít soubor DSL uvnitř [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ale soubor nelze otevřít z Průzkumníka Windows.

#### <a name="to-install-a-dsl-by-using-the-vsx"></a>Instalace DSL pomocí VSX

1.  V počítači, vyhledejte **VSIX** soubor, který byl vytvořený pomocí projektu DSL balíčku.

    1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DslPackage** projektu a pak klikněte na **otevřít složku v Průzkumníku Windows**.

    2.  Vyhledejte soubor **bin\\\*\\***YourProject***. DslPackage.vsix**

2.  Kopírování **VSIX** souboru k cílovému počítači, na kterém chcete nainstalovat DSL. To může být svého počítače nebo jiný.

    -   Cílový počítač musí mít jednu z edicí systému [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] podporující DSL, linky za běhu. Další informace najdete v tématu [podporována edice Visual Studio pro vizualizace a modelování SDK](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md).

    -   Cílový počítač musí mít jednu z edicí systému [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zadaný v **DslPackage\source.extensions.manifest**.

3.  Na cílovém počítači, dvakrát klikněte **VSIX** souboru.

     **Instalační program Visual Studio rozšíření** otevře a instalaci rozšíření.

4.  Spusťte nebo restartujte [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].

5.  Chcete-li otestovat DSL, použijte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] k vytvoření nového souboru, který má příponu, který jste zadali pro vaše DSL.

#### <a name="to-uninstall-a-dsl-that-was-installed-by-using-vsx"></a>Chcete-li odinstalovat DSL, která byla nainstalována pomocí VSX

1.  Na **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**.

2.  Rozbalte položku **nainstalovaná rozšíření**.

3.  Vyberte rozšíření, ve kterém je definovaný DSL a pak klikněte na tlačítko **odinstalovat**.

 Zřídka vadný rozšíření nepodaří načíst a vytvoří sestavu ve okno chyby, ale nezobrazí ve Správci rozšíření. V takovém případě můžete rozšíření odebrat odstraněním souboru:

 *LocalAppData* **\Microsoft\VisualStudio\10.0\Extensions**

##  <a name="msi"></a> Nasazení DSL v souboru MSI
 Definováním soubor MSI (Instalační služba systému Windows) pro vaše DSL, můžete povolit uživatelům otevřít soubory DSL z Průzkumníka Windows. Můžete také přidružit ikonu a krátký popis vaše přípona názvu souboru. Soubor MSI kromě toho můžete nainstalovat XSD, který slouží k ověření DSL soubory. Pokud chcete, můžete přidat další součásti do MSI, který bude nainstalován ve stejnou dobu.

 Další informace o souborech MSI a jiné možnosti nasazení najdete v tématu [nasazení aplikací, služeb a komponent](../deployment/deploying-applications-services-and-components.md).

 K vytvoření souboru MSI, můžete přidat do projektu instalace vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení. Nejsnazší vytvoření projektu instalace je použít CreateMsiSetupProject.tt šablonu, kterou si můžete stáhnout z [VMSDK lokality](http://go.microsoft.com/fwlink/?LinkID=186128).

#### <a name="to-deploy-a-dsl-in-an-msi"></a>K nasazení DSL v souboru MSI

1.  Nastavit `InstalledByMsi` v manifestu rozšíření. To brání VSX se instaluje a odinstaluje kromě podle soubor MSI. To je důležité, pokud bude obsahovat další součásti v soubor MSI.

    1.  Open DslPackage\source.extension.tt

    2.  Vložte následující řádek před `<SupportedProducts>`:

        ```
        <InstalledByMsi>true</InstalledByMsi>
        ```

2.  Vytvořte nebo upravte ikonu, která bude představovat váš DSL v Průzkumníku Windows. Můžete třeba upravit **DslPackage\Resources\File.ico**

3.  Zajistěte, aby byla následující atributy vaší DSL správné:

    -   V Průzkumníku DSL klikněte na kořenový uzel a v okně Vlastnosti zkontrolujte:

        -   Popis

        -   Version

    -   Klikněte **Editor** uzel a v okně vlastností klikněte na tlačítko **ikonu**. Nastavit hodnotu tak, aby odkazovaly soubor ikony v **DslPackage\Resources**, jako například **File.ico**

    -   Na **sestavení** nabídce otevřete **nástroje Configuration Manager**a vyberte konfiguraci, kterou chcete vytvořit, jako například **verze** nebo **ladění** .

4.  Přejděte na [vizualizace a modelování SDK domovskou stránku](http://go.microsoft.com/fwlink/?LinkID=186128)a z **stáhne** kartě, stáhněte si **CreateMsiSetupProject.tt**.

5.  Přidat **CreateMsiSetupProject.tt** do projektu Dsl.

     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Vytvoří soubor s názvem **CreateMsiSetupProject.vdproj**.

6.  V Průzkumníku Windows, zkopírujte Dsl\\\*.vdproj do nové složky s názvem instalační program.

     (Pokud chcete, můžete nyní vyloučit CreateMsiSetupProject.tt z projektu Dsl.)

7.  V **Průzkumníku řešení**, přidejte **instalace\\\*.vdproj** jako existujícího projektu.

8.  Na **projektu** nabídky, klikněte na tlačítko **závislosti projektu**.

     V **závislosti projektu** dialogovém okně vyberte projekt instalace.

     Zaškrtněte políčko vedle **DslPackage**.

9. Znovu sestavte řešení.

10. V Průzkumníku Windows vyhledejte soubor MSI integrované ve vašem projektu instalace.

     Zkopírujte soubor MSI do počítače, na kterém chcete nainstalovat vaší DSL. Poklikejte na soubor MSI. Instalační program se spustí.

11. V cílovém počítači vytvořte nový soubor, který má příponu vaší DSL. Ověřte, že:

    -   Soubor se v zobrazení seznamu Průzkumníka Windows, zobrazí se ikona a popis, který jste definovali.

    -   Když dvakrát kliknete na soubor, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] spustí a otevře DSL souboru ve svém DSL editoru.

 Pokud dáváte přednost, můžete vytvořit projekt instalace ručně, místo použití textové šablony. Návod, který obsahuje tento postup naleznete v kapitole 5 z [vizualizace a modelování Lab SDK](http://go.microsoft.com/fwlink/?LinkId=208878).

#### <a name="to-uninstall-a-dsl-that-was-installed-from-an-msi"></a>Chcete-li odinstalovat DSL, která byla nainstalována ze souboru MSI

1.  V systému Windows, otevřete **programy a funkce** ovládací panely.

2.  Odinstalujte DSL.

3.  Restartujte sadu Visual Studio.