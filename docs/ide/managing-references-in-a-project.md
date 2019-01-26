---
title: Správa odkazů v projektu
ms.date: 04/11/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.ProjectPropertiesReferencePaths
- cs.ProjectPropertiesReferencePaths
helpviewer_keywords:
- C# projects, references
- referencing objects, project references
- external component references
- referencing namespaces
- Visual Basic projects, references
- referencing components, external components
- Web references, types of project references
- namespaces [Visual Studio], referencing
- COM components, referencing
- objects [Visual Studio], referencing
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3612e3b04fc27460922f90e48666397ce9fb3b73
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55042983"
---
# <a name="manage-references-in-a-project"></a>Správa odkazů v projektu

Předtím, než můžete napsat kód proti externí komponentě nebo připojené služby, váš projekt musí nejprve obsahovat odkaz na jeho. Odkaz je v podstatě záznam v souboru projektu, který obsahuje informace, že Visual Studio potřebuje najít komponentu nebo službu.

Přidání odkazu, klikněte pravým tlačítkem na **odkazy** nebo **závislosti** uzel v **Průzkumníka řešení** a zvolte **přidat odkaz**. Můžete také kliknout pravým tlačítkem na uzel projektu a vyberte **přidat** > **odkaz**. Další informace najdete v tématu [jak: Přidání nebo odebrání odkazů](../ide/how-to-add-or-remove-references-by-using-the-reference-manager.md).

![Přidání odkazu v jazyce Visual C&#43;&#43;](../ide/media/vs2015_cpp_add_reference.png)

Můžete přidat odkaz na následující typy komponent a služeb:

- Knihovny tříd rozhraní .NET framework nebo sestavení

- U aplikací pro UPW

- COM – součásti

- Jiné sestavení nebo knihovny tříd projektů ve stejném řešení

- webové služby XML

## <a name="uwp-app-references"></a>Odkazy na aplikace pro UPW

### <a name="project-references"></a>Odkazy na projekt

Projekty pro Universal Windows Platform (UWP) můžete vytvořit odkazy na jiné projekty UWP v řešení nebo projekty Windows 8.1 nebo binární soubory, za předpokladu, že tyto projekty nepoužívají rozhraní API, která se již nepoužívají v systému Windows 10. Další informace najdete v tématu [přesunout z Windows 8 modulu Runtime pro UPW](/windows/uwp/porting/w8x-to-uwp-root).

Pokud budete chtít změnit cílení projektů pro Windows 8.1 na Windows 10, najdete v článku [Port, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md).

### <a name="extension-sdk-references"></a>Odkazy na rozšíření SDK

V jazyce Visual Basic C#, C++ a JavaScript Universal Windows Platform (UPW) aplikace můžete odkazovat na rozšíření SDK, které cílí na Windows 8.1, tak dlouho, dokud tato rozšíření sady SDK nepoužívají rozhraní API, která se již nepoužívají v systému Windows 10. Zkontrolujte web dodavatele rozšíření SDK a zjistěte, zda jej lze odkazovat v aplikacích pro UPW.

Pokud zjistíte, že není podporováno rozšíření SDK, které odkazuje vaše aplikace, je nutné provést následující kroky:

1. Podívejte se na název projektu, který je příčinou chyby. Platformy, na kterou váš projekt je cílen na verzi je uvedena v závorkách vedle názvu projektu. Například **MyProjectName (Windows 8.1)** znamená, že váš projekt **MyProjectName** je zaměřen na verzi platformy Windows 8.1.

1. Přejděte na web dodavatele, který vlastní nepodporovanou sadu SDK rozšíření a nainstalujte verzi sady SDK rozšíření se závislostmi, které jsou kompatibilní s verzí platformy, na kterou váš projekt cílí.

    > [!NOTE]
    > Jeden způsob, jak zjistit, zda rozšíření SDK má závislosti na dalších rozšířeních SDK, je hledání v **správce odkazů**. Restartujte sadu Visual Studio, vytvořte nový C# aplikace pro UPW v projektu a potom klikněte pravým tlačítkem na projekt a zvolte možnost **přidat odkaz**. Přejděte **Windows** kartu, pak bude **rozšíření** dílčí kartě a vyberte rozšíření SDK. Podívejte se na v pravém podokně **správce odkazů**. Pokud existují závislosti, budou uvedeny zde.

    > [!IMPORTANT]
    > Pokud váš projekt je cílen na verzi Windows 10 a v předchozím kroku nainstalované rozšíření SDK obsahuje závislost na balíčku Microsoft Visual C++ Runtime, verze balíčku Microsoft Visual C++ Runtime, který je kompatibilní s Windows 10 je v14.0 a je nainstalovaná pomocí sady Visual Studio.

1. Pokud jste v předchozím kroku nainstalované rozšíření SDK má závislosti na dalších rozšířeních SDK, přejděte na weby dodavatelů, kteří závislosti vlastní a nainstalujte verze těchto závislostí, které jsou kompatibilní s verzí platformy, na kterou váš projekt je cílem.

1. Restartujte Visual Studio a otevřete aplikaci.

1. Klikněte pravým tlačítkem na **odkazy** nebo **závislosti** uzlu v projektu, který způsobil chybu a zvolte **přidat odkaz**.

1. Klikněte na tlačítko **Windows** kartu a potom **rozšíření** dílčí kartu, poté zrušte zaškrtnutí políček pro staré SDK rozšíření a zaškrtněte políčka pro nové SDK rozšíření. Klikněte na **OK**.

## <a name="add-a-reference-at-design-time"></a>Přidat odkaz v době návrhu

Pokud odkaz na sestavení v projektu, Visual Studio vyhledá sestavení v následujících umístěních:

- Aktuální adresář projektu. (Můžete vyhledat tato sestavení pomocí **Procházet** tab.)

- Další adresáře projektu ve stejném řešení. (Můžete vyhledat tato sestavení na **projekty** tab.)

> [!NOTE]
> - Všechny projekty obsahují implicitní odkaz na **mscorlib**.
> - Všechny projekty obsahují implicitní odkaz na `System.Core`i v případě `System.Core` se odebere ze seznamu odkazů.
> - Projekty Visual Basic obsahují implicitní odkaz na <xref:Microsoft.VisualBasic>.

## <a name="references-to-shared-components-at-run-time"></a>Odkazy na sdílené komponenty za běhu

V době běhu součásti musí být buď v cestě výstupu projektu nebo v globální mezipaměti sestavení (GAC). Pokud projekt obsahuje odkaz na objekt, který se nenachází v jednom z těchto umístění, musíte zkopírovat odkaz na výstupní cestu k projektu při sestavování projektu. <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> Vlastnost určuje, zda tato kopie má být provedena. Pokud je hodnota **True**, odkaz je zkopírován do adresáře projektu při sestavování projektu. Pokud je hodnota **False**, odkaz není kopírován.

Pokud nasadíte aplikaci, která obsahuje odkaz na vlastní komponentu registrovanou v mezipaměti GAC, komponenta nebude nasazena s aplikací bez ohledu na to <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> nastavení. V dřívějších verzích sady Visual Studio, můžete nastavit <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> vlastnost v odkazu k zajištění toho, že bylo sestavení nasazeno. Nyní je třeba ručně přidat sestavení do složky \Bin. To umístí všechny vlastní kódy pod kontrolu, což zmenší riziko publikování vlastního kódu, se kterým nejste obeznámeni.

Ve výchozím nastavení <xref:Microsoft.VisualStudio.VCProjectEngine.VCProjectReference.CopyLocal%2A> je nastavena na **False** Pokud sestavení nebo komponenta v globální mezipaměti sestavení, nebo je komponentou architektury. V opačném případě je hodnota nastavena na **True**. Odkazy typu projekt projekt jsou vždy nastaveny na **True**.

## <a name="reference-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Odkaz na projekt nebo sestavení, které cílí na jinou verzi rozhraní .NET Framework

Můžete vytvářet aplikace, které odkazují na projekty nebo sestavení, která je jiná cílová verze rozhraní .NET Framework. Například můžete vytvořit aplikaci cíleného rozhraní .NET Framework 4.6, které odkazuje na sestavení, které cílí na rozhraní .NET Framework 4.5. Pokud vytvoříte projekt, který se zaměřuje na starší verzi rozhraní .NET Framework, nemůžete nastavit odkaz v projektu na projekt nebo sestavení, který se zaměřuje na novější verzi.

Další informace najdete v tématu [přehled multiplatformního zacílení](../ide/visual-studio-multi-targeting-overview.md).

## <a name="project-to-project-references"></a>Projekt pro odkazy na projekt

Odkazy typu projekt projekt jsou odkazy na projekty obsahující sestavení; Vytvoření s použitím **projektu** kartu. Sada Visual Studio můžete najít sestavení při zadané cestě do projektu.

Pokud máte projekt, který vytváří sestavení, by měla odkazovat na projekt a nepoužívat odkaz na soubor (viz níže). Výhodou odkazu typu projekt projekt je, že vytvoří závislost mezi projekty v systému sestavení. Závislý projekt bude vytvořen, pokud se změnil od posledního odkazujícího projektu. Odkaz na soubor nevytváří závislost sestavení, takže je možné sestavit odkazující projekt bez vytváření závislého projektu a odkaz se může stát zastaralým. (To znamená, že projekt může odkazovat na dřívější sestavené verze projektu.) Může dojít k několika verzí jednoho souboru knihovny DLL v nich vyžaduje *bin* adresáře, který není možné. Pokud dojde k tomuto konfliktu, zobrazí se zpráva, jako "Upozornění: závislost 'file' v projektu 'project' nelze zkopírovat do běhového adresáře, protože by přepsala odkaz 'file'.". Další informace najdete v tématu [nefunkční odkazy na řešení potíží](../ide/troubleshooting-broken-references.md) a [jak: Vytváření a odebrání závislostí projektu](../ide/how-to-create-and-remove-project-dependencies.md).

> [!NOTE]
> Odkaz na soubor místo odkazu typu projekt projekt je vytvořen, pokud cílová verze rozhraní .NET Framework jednoho projektu je verze 4.5 a cílová verze jiného projektu je verze 2, 3, 3.5 nebo 4.0.

## <a name="file-references"></a>Odkazy na soubory

Odkazy na soubory jsou přímé odkazy na sestavení mimo kontext projektu ve Visual Studiu. Vytvoření s použitím **Procházet** karty **správce odkazů**. Používejte odkaz na soubor, pokud máte jenom sestavení nebo komponentu a ne projekt, který vytvoří jako výstup.

## <a name="see-also"></a>Viz také:

- [Řešení problémů s poškozenými odkazy](../ide/troubleshooting-broken-references.md)
- [Postupy: Přidání nebo odebrání odkazů](../ide/how-to-add-or-remove-references-by-using-the-reference-manager.md)
