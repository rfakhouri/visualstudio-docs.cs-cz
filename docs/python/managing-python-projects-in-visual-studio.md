---
title: "Správa projektů pro Python aplikace v sadě Visual Studio | Microsoft Docs"
description: "Vysvětlující účel projekty v sadě Visual Studio, ukazuje, jak vytvořit a spravovat projekty pro kód Python a popisuje jiný projekt šablony dostupné pro jazyk Python."
ms.custom: 
ms.date: 02/15/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: aafb2259ec4f16341abf514e9496dbb66f3cb95c
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2018
---
# <a name="python-projects"></a>Projektů v jazyce Python

Aplikace Python jsou obvykle definovány pomocí pouze složky a soubory, ale může být tato struktura složitá, jak je aplikace, se zvětšit a případně zahrnují automaticky generovaný soubory JavaScript pro webové aplikace a tak dále. Projekt sady Visual Studio pomáhá spravovat Tato složitost. Projekt ( `.pyproj` souboru) identifikuje všechny zdroje a soubory obsahu přidružené k projektu, obsahuje informace o sestavení pro každý soubor, udržuje informace o integraci se systémy správy zdrojového kódu a pomáhá uspořádat vaší aplikace do logické součásti.

![Projekt Python v Průzkumníku řešení](media/projects-solution-explorer.png)

Kromě toho jsou vždy spravované projekty v sadě Visual Studio *řešení*, která může obsahovat libovolný počet projekty, které může odkazovat na sebe navzájem. Například projekt Python, můžete odkazovat projektu jazyka C++, která implementuje modul rozšíření. S tuto relaci sady Visual Studio automaticky sestavení projektu C++ (v případě potřeby) při spuštění ladění projektu Python. (Obecné informace, naleznete v [řešení a projektů v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md).)

Visual Studio poskytuje řadu šablon projektu Python rychle nastavit počet struktury aplikace, včetně šablonu pro vytvoření projektu z existujících stromovou strukturu složek a šablonu pro vytvoření projektu čistá, prázdný. V tématu [šablony projektu](#project-templates) pro index.

<a name="lightweight-usage-project-free"></a>

> [!Tip]
> I bez projektu Visual Studio funguje dobře s kódem jazyka Python. Například můžete otevřít Python souboru samostatně a získejte automatické doplňování, IntelliSense a ladění (v editoru pravým tlačítkem myši a výběrem **spuštění [s | bez] ladění**). Protože takový kód vždy používá výchozího globálního prostředí, ale může se zobrazit nesprávný dokončování nebo chyby Pokud kód je určená pro jinou prostředí. Kromě toho Visual Studio analyzuje všechny soubory a balíčky v složky, ve kterém je otevřen jeden soubor, který může spotřebovat značnou část času procesoru.
>
> Je jednoduché vytvořit projekt sady Visual Studio z existujícího kódu, jak je popsáno v [vytvoření projektu z existujících souborů](#creating-a-project-from-existing-files).

|   |   |
|---|---|
| ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Getting-Python-Code-iLAv23LWE_3905918567) Úvod do projektů v jazyce Python (2 m 17s). |
| ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video") | Viz také [podrobné informace: Správa zdrojového kódu pomocí projektů v jazyce Python](https://youtu.be/Aq8eqApnugM) (webu youtube.com, 8 m 55s). |

## <a name="adding-files-assigning-a-startup-file-and-setting-environments"></a>Přidávání souborů, přiřazení spouštění souborů a nastavení prostředí

Když budete vyvíjet aplikace, musíte obvykle do projektu přidejte nové soubory různých typů. Přidání tyto soubory se provádí kliknutím pravým tlačítkem na projekt a výběrem **Přidat > existující položka...** . pomocí které můžete vyhledat soubor, který chcete přidat, nebo **Přidat > novou položku...** , který zobrazí dialogové okno s různými šablon položek. Šablony zahrnují soubory prázdný python, třídu python, testování částí a různé soubory vztahující se k webovým aplikacím. Tyto možnosti se testovacího projektu se dozvíte, co je k dispozici ve vaší verzi sady Visual Studio můžete prozkoumat.

Každý projekt Python má jeden soubor přiřazené spuštění zobrazeny tučným v Průzkumníku řešení. Spouštěcí soubor je soubor, který se spustí při spuštění ladění (F5 nebo **ladění > Spustit ladění**) nebo při spuštění projektu v okně interaktivní (Shift + Alt + F5 nebo **ladění > spustit projekt v Pythonu Interaktivní**). Chcete-li ji změnit, klikněte pravým tlačítkem na nový soubor a vyberte **nastavit jako spouštěcí soubor**.

> [!Tip]
> Když odeberete vybranou spouštěcí soubor z projektu a nevybírejte nový, spuštění projektu výsledky v Python výstup okna zobrazování, ale pak zmizení téměř okamžitě. Pokud narazíte na toto chování, zkontrolujte, že budete mít soubor přiřazené spuštění. Navíc pokud chcete zachovat ve výstupním okně Otevřít v takových případech, klikněte pravým tlačítkem na projekt, vyberte možnost **vlastnosti**, vyberte **ladění** kartě a pak přidejte `-i` k **překladač argumenty** pole. Tento argument způsobí, že překladač uvést do režimu interaktivní po dokončení programu, a tím zprovozní okno Otevřít zadejte Ctrl + Z, zadejte ukončíte.

Nový projekt je vždy přidružen prostředí výchozí globální Python. Chcete-li přidružit projektu do různých prostředí (včetně virtuální prostředí), klikněte pravým tlačítkem na s **prostředí Python** uzlu v projektu, vyberte **prostředí Python přidat nebo odebrat**, a Vyberte ty, které chcete. Chcete-li změnit aktivního prostředí, klikněte pravým tlačítkem na požadované prostředí a vyberte **aktivovat prostředí** jak je uvedeno níže. Další informace najdete v tématu [prostředí Python](managing-python-environments-in-visual-studio.md#selecting-an-environment-for-a-project).

![Aktivace prostředí pro projekt Python](media/projects-activate-environment.png)

<a name="project-types"</a>

## <a name="project-templates"></a>Šablony projektů

Visual Studio poskytuje několik způsobů, jak nastavit projekt Python, od začátku, nebo z existujícího kódu. Chcete-li použít šablonu, vyberte **soubor > Nový > projekt...**  příkaz nabídky nebo klikněte pravým tlačítkem na řešení v Průzkumníku řešení a vyberte **Přidat > Nový projekt...** , které obě zprovoznit **nový projekt** dialogu níže. Specifické pro Python šablony zobrazíte hledání "Python" nebo vyberte **nainstalovaná > Python** uzlu:

![Dialogové okno Nový projekt se šablonami Python](media/projects-new-project-dialog.png)

Následující tabulka shrnuje šablony dostupné na Visual Studio 2017 (ne všechny šablony jsou dostupné v všechny předchozí verze):

| Šablony | Popis |
| --- | --- |
| [Z existujícího kódu jazyka Python](#creating-a-project-from-existing-files) | Projekt sady Visual Studio vytvoří z existujícího kódu Python ve struktuře složek.  |
| Aplikace Python | Struktura základního projektu pro novou aplikaci Python s jeden, prázdný zdrojového souboru. Ve výchozím projektu spouští v konzole překladač výchozí globální prostředí, které můžete změnit [přiřazení do různých prostředí](managing-python-environments-in-visual-studio.md#selecting-an-environment-for-a-project). |
| [Cloudové služby Azure](python-azure-cloud-service-project-template.md) | Projekt pro cloudové služby Azure napsané v Pythonu. |
| [Webové projekty](python-web-application-project-templates.md) | Projekty pro webové servery založené na různé platformy, včetně charakteristické znaky Bottle, Flask a Django Flask/Jade. |
| IronPython aplikace | Podobně jako šablona aplikací Python, ale používá IronPython ve výchozí povolení rozhraní .NET spolupráce a ve smíšeném režimu ladění s jazyky rozhraní .NET. |
| Aplikace IronPython WPF | Struktura projektu pomocí IronPython soubory Windows Presentation Foundation XAML pro uživatelské rozhraní aplikace. Visual Studio poskytuje návrháře XAML uživatelského rozhraní, kódu může být napsané v Pythonu a spuštění aplikace bez zobrazení konzoly. |
| IronPython Silverlight webové stránky | Projekt IronPython, který běží v prohlížeči pomocí programu Silverlight. Kód aplikace Python je součástí webové stránky jako skript. Vrátí značku skriptu standardní dolů určitý kód JavaScript, která inicializuje IronPython systémem uvnitř Silverlight, ze kterého může váš kód Python zasahovat modelu DOM. |
| Aplikaci IronPython Windows Forms | Struktura projektu pomocí IronPython withUI vytvoření kódu pomocí Windows Forms. Aplikace běží bez zobrazení konzoly. |
| Aplikace na pozadí (IoT) | Podporuje nasazení projektů v jazyce Python spustit jako služby na pozadí na zařízení. Přejděte [Centrum vývojářů pro Windows IoT](https://dev.windows.com/en-us/iot) Další informace. |
| Modul rozšíření Python | Tato šablona se zobrazí pod Visual C++, pokud jste nainstalovali **Python tools nativní vývoj** se zatížením Python ve Visual Studio 2017 (najdete v části [instalace](installing-python-support-in-visual-studio.md)). Poskytuje základní strukturu pro rozšíření C++ knihovny DLL, podobně jako co je popsáno na [vytváření rozšíření pro C++ pro jazyk Python](working-with-c-cpp-python-in-visual-studio.md). |

> [!Note]
> Protože Python je interpretovaný jazyk, Python projekty v sadě Visual Studio nepřispívají k samostatnému spustitelnému souboru jako další projekty kompilované jazyka (C#, např.). Další informace najdete v tématu [otázky a odpovědi](overview-of-python-tools-for-visual-studio.md#questions-and-answers).

<a name="create-project-from-existing-files"</a>

### <a name="creating-a-project-from-existing-files"></a>Vytvoření projektu z existujících souborů

> [!Important]
> Proces popsaný tady není přesuňte nebo zkopírujte původním zdrojovým souborům. Pokud chcete pracovat s kopií, duplicitní nejprve složce.

[!INCLUDE[project-from-existing](includes/project-from-existing.md)]

## <a name="linked-files"></a>Připojené soubory

Propojené soubory jsou soubory, které jsou uvedeny do projektu, ale mimo složky projektu aplikace jsou obvykle umístěny. Jsou zobrazeny v Průzkumníkovi řešení jako normální soubory ikonou překryté zástupce: ![Ikona připojený soubor](media/projects-linked-file-icon.png)

Připojené soubory jsou určené v `.pyproj` souboru pomocí `<Compile Include="...">` elementu. Implicitní, pokud používají mimo strukturu adresáře na relativní cestu nebo explicitní, pokud používají cesty v Průzkumníku řešení jsou propojené soubory:

```xml
<Compile Include="..\test2.py">
    <Link>MyProject\test2.py</Link>
</Compile>
```

Připojené soubory jsou ignorovány ve všech následujících podmínek:

- Odkazovaný soubor obsahuje odkaz metadata a Cesta zadaná v život atribut zahrnutí v adresáři projektu
- Připojený soubor duplikuje soubor, který existuje v rámci hierarchie projektu
- Připojený soubor obsahuje odkaz metadata a odkaz cesta je relativní cesta mimo hierarchii projektu
- Cesta odkazu je root.

### <a name="working-with-linked-files"></a>Práce s připojené soubory

Chcete-li přidat existující položku jako odkaz, klikněte pravým tlačítkem na složku v projektu, kam chcete soubor přidat a pak vyberte **Přidat > ukončení položky...** . V dialogovém okně se zobrazí, vyberte soubor a zvolte **přidat jako odkaz** z rozevíracího seznamu na **přidat** tlačítko. Za předpokladu, že nejsou žádné konfliktní soubory, tento příkaz vytvoří odkaz ve vybrané složce. Odkaz není však přidat, pokud již soubor se stejným názvem nebo odkaz na daný soubor již existuje v projektu.

Pokud budete chtít vytvořit odkaz na soubor, který už v projektu složky, se přidá jako normální soubor a ne jako odkaz. Chcete-li převést odkaz na soubor, vyberte **soubor > Uložit jako** k uložení souboru do umístění mimo hierarchii projektu; Visual Studio automaticky převede jej na odkaz. Podobně můžete převést odkaz zpět pomocí **soubor > Uložit jako** k uložení souboru někde v rámci hierarchie projektu. 

Pokud přesunete připojený soubor v Průzkumníku řešení, k přesunutí, ale skutečný soubor je poškozena. Podobně odstraňování odkaz odebere propojení bez ovlivnění soubor.

Propojených souborů nelze přejmenovat.

## <a name="references"></a>Odkazy

Podpora přidávání odkazů na projekty a rozšíření, která se zobrazí pod projektů sady Visual Studio **odkazy** uzlu v Průzkumníku řešení:

![Reference na rozšíření v projektů v jazyce Python](media/projects-extension-references.png)

Reference na rozšíření obvykle označuje závislosti mezi projekty a slouží k poskytování technologie IntelliSense v době návrhu nebo propojení v době kompilace. Projektů v jazyce Python použít odkazy podobným způsobem, ale vzhledem k povaze dynamické jazyka Python se primárně používají v době návrhu zajistit lepší IntelliSense. Můžete také používají pro nasazení do služby Microsoft Azure nainstalovat další závislosti.

### <a name="extension-modules"></a>Rozšíření modulů

Odkaz na `.pyd` souboru umožňuje technologii IntelliSense pro modul vygenerovaný. Načte Visual Studio `.pyd` soubor je načtena do překladač Pythonu a introspects jeho typy a funkce. Taky automatický pokus o Analýza řetězců dokumentů pro funkce k poskytnutí nápovědy podpis.

Pokud modul rozšíření je kdykoli aktualizovat na disku, Visual Studio znovu analyzovala modul na pozadí. Tato akce nemá žádný vliv na chování za běhu, ale některé dokončených nejsou k dispozici, dokud se nedokončí analýzy.

Také můžete potřebovat pro přidání [cesty pro hledání](managing-python-environments-in-visual-studio.md#search-paths) do složky obsahující modul.

### <a name="net-projects"></a>Projekty rozhraní .NET

Při práci s IronPython, můžete přidat odkazy na sestavení .NET povolení technologie IntelliSense. .NET projekty v řešení, klikněte pravým tlačítkem myši **odkazy** uzlu v projektu jazyka Python, vyberte **přidat odkaz na**, vyberte **projekty** kartě a přejděte do požadované projektu. Pro knihovny DLL, které jste stáhli samostatně, vyberte **Procházet** kartě místo a přejděte na knihovnu DLL požadovanou.

Protože odkazů v IronPython nejsou k dispozici až volání `clr.AddReference('AssemblyName')` je proveden, musíte taky přidat `clr.AddReference` volání sestavení.

### <a name="webpi-projects"></a>Projekty WebPI

Odkazy na záznamy produktu WebPI pro nasazení můžete přidat do Microsoft Azure Cloud Services, kde můžete nainstalovat další součásti prostřednictvím WebPI informačního kanálu. Ve výchozím kanálu zobrazí specifické pro Python a zahrnuje Django, CPython a další komponenty jádra. Můžete také vybrat vlastní informační kanál, jak je uvedeno níže. Při publikování do služby Microsoft Azure, úlohu instalační program nainstaluje všechny odkazované produkty.

![Odkazy na WebPI](media/projects-webPI-components.png)