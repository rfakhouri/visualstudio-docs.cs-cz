---
title: Návrh XAML v aplikaci Visual Studio a Blend
titleSuffix: ''
ms.date: 08/05/2019
ms.topic: conceptual
ms.assetid: 288e2415-9fcf-408e-bc35-9848315e14fd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cd0ff12b141a50872d586764d2b33bd68f3224fb
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821870"
---
# <a name="design-xaml-in-visual-studio-and-blend-for-visual-studio"></a>Návrh XAML v aplikaci Visual Studio a Blend pro Visual Studio

Visual Studio a Blend for Visual Studio poskytují vizuální nástroje pro sestavování poutavější uživatelské rozhraní a bohatý mediální prostředí s XAML pro širokou škálu typů aplikací. Jak integrované vývojové prostředí (IDE) sdílí společnou sadu funkcí, včetně editoru Visual XAML (Designer). Blend pro Visual Studio, který podporuje platformy WPF a UWP, poskytuje další nástroje pro návrh vizuálních stavů a vytváření animací.

Můžete přepínat mezi Visual Studio a Blend pro Visual Studio a můžete dokonce i mít stejný projekt otevřený v obou prostředích ve stejnou dobu. Změny uložené do souborů XAML v jednom rozhraní IDE lze použít prostřednictvím automatického opětovného načtení při přepnutí na jiné integrované vývojové prostředí (IDE). Způsob opětovného načtení můžete řídit tak, že přejdete na **nástroje** > **Možnosti** > pro**dokumenty** **prostředí** > v obou IDE.

## <a name="installation"></a>Instalace

- Pokud chcete vytvářet aplikace WPF, nainstalujte do sady Visual Studio úlohu **vývoj desktopových** aplikací pro .NET. Nainstaluje se taky Blend pro Visual Studio.
- Pokud chcete vytvářet aplikace pro UWP, nainstalujte **Univerzální platforma Windows vývojové** úlohy v aplikaci Visual Studio. Nainstaluje se taky Blend pro Visual Studio.
- K vytváření aplikací Xamarin. Forms nainstalujte **vývoj mobilních aplikací pomocí technologie .NET** v aplikaci Visual Studio. Blend pro Visual Studio není nainstalováno. Blend nepodporuje aplikace Xamarin. Forms.

## <a name="shared-capabilities"></a>Sdílené možnosti

Pro většinu základních úloh vývoje aplikace Visual Studio a Blend pro Visual Studio sdílí stejnou sadu Windows a možností s některými drobnými rozdíly. Mezi nejdůležitější funkce patří:

- **IntelliSense** V obou prostředích podporuje funkce IntelliSense, jako je například dokončování příkazů.

- **Ladění:** Můžete ladit v [aplikaci Visual Studio](../debugger/inspect-xaml-properties-while-debugging.md) a [Blend pro Visual Studio](../debugger/debug-xaml-in-blend.md), včetně nastavení zarážek v kódu pro ladění spuštěné aplikace a pomocí [horkého opětovného načtení](../debugger/xaml-hot-reload.md) ke změně kódu XAML v době, kdy aplikace běží. Zachování konzistentní možnosti ladění pomocí sady Visual Studio, nástroje Blend for Visual Studio obsahuje většinu ladění systému windows a panelů nástrojů sady Visual Studio.

- **Opětovné načtení souboru:** Soubory XAML můžete upravovat buď v aplikaci Visual Studio, nebo v Blend pro Visual Studio. Upravené soubory, které byly uloženy, se automaticky znovu načítají při přepínání mezi prostředím IDEs. Způsob opětovného načtení můžete řídit tak, že přejdete na **nástroje** > **Možnosti** > pro**dokumenty** **prostředí** > v obou IDE.

- **Synchronizovaná rozložení a nastavení:** Přizpůsobené rozložení a nastavení oken nástrojů pro Visual Studio nebo Blend pro Visual Studio se synchronizují napříč vašimi zařízeními a verzemi, když se přihlásíte pomocí stejného účtu přizpůsobení. Zobrazit [synchronizaci nastavení mezi více počítači](../ide/synchronized-settings-in-visual-studio.md).

## <a name="advanced-capabilities-in-blend-for-visual-studio"></a>Pokročilé možnosti v Blend pro Visual Studio

Pokud chcete zvýšit vaši produktivitu, vezměte v úvahu pomocí nástroje Blend for Visual Studio pro následující úlohy. Jedná se o oblasti, kde Blend pro Visual Studio nabízí více funkcí, než je Návrhář sady Visual Studio nebo samotný kód.

| Úloha | Visual Studio | Blend for Visual Studio | Další informace |
| - | - | - | - |
| **Návrh vizuálních stavů** | Neexistuje žádný nástroj, který by vám mohl pomáhat s návrhem vizuálních stavů. je nutné je vytvořit programově. | Pomocí návrhových nástrojů můžete změnit vzhled ovládacího prvku na základě jeho stavu. | [Vizuální stavy](modify-the-style-of-objects-in-blend.md#visual-states) |
| **Vytváření animací** |Neexistuje žádná návrhářský nástroj pro animace; je nutné je vytvořit prostřednictvím kódu programu. To vyžaduje pochopení animace a časování systému v projektech WPF a rozsáhlé znalosti kódování.|Vizuálně vytvářet animace a můžete si zobrazte jejich náhled v programu Blend for Visual Studio. Toto je rychlejší a přesnější, než vytváření animace v kódu. Můžete přidat aktivační události na zpracovávají interakci s uživatelem, a můžete přepnout na kód pro přidání obslužné rutiny událostí a další funkce.|[Animace objektů](../designers/animate-objects-in-xaml-designer.md)|
|**Proměňte cesty ke snadnější práci s tvary a text**|Není podporováno.|Drobné nebo výrazné změny můžete provádět obrazce (například obdélníky a tři tečky) převedením na cesty, které poskytují lepší úprav ovládacího prvku. Můžete změnit tvar nebo kombinace cesty a vytvořit složené cesty z více tvarů.<br /><br />Bloky textu můžete také převést do cesty k manipulaci s nimi jako vektorové obrázky.|[Kreslení tvarů a cest](../designers/draw-shapes-and-paths.md)|
|**Upravit ovládací prvky, šablony a styly**|Vyžaduje kódování a znalost WPF – styly a šablony.|Zapněte všechny bitové kopie do ovládacího prvku.<br /><br />Pomocí nástroje pro úpravy šablon provádět změny na ovládací prvky, styly a šablony pomocí několika kliknutí myší.<br /><br />Například můžete použít nástroj Blend for Visual Studio prostředků stylu k implementaci běžných ovládacích prvků WPF (například tlačítka, seznamy, posuvníky, nabídkách atd.) a změnit jejich barva, styl nebo základní šablony přímo v programu Blend for Visual Studio. Pokud chcete, můžete kód pro doladění poté přejděte.|[Úpravy stylu objektů](../designers/modify-the-style-of-objects-in-blend.md)|
|**Vaše uživatelské rozhraní se připojit k datům**|Můžete vytvořit zdroj dat z prostředků, jako jsou SQL Server databáze, WCF nebo webová služba, objekt nebo SharePointový seznam, a pak vytvořit propojení zdroje dat s ovládacími prvky uživatelského rozhraní.<br /><br />Dat doby návrhu musí být vytvořeny ručně pro interaktivní návrhové prostředí.|Pro .NET Framework aplikace Vytvářejte ukázková data snadno pro vytváření prototypů a testování. Přepnout na živá data, jakmile budete připraveni.<br /><br />Blend pro vytvoření datové sady Visual Studio možnosti nejsou vyřízeny (můžete přidat názvy, čísla, adresy URL a fotografie snadno za chodu) a ušetřit spoustu času.<br /><br />Pro dynamická data můžete svázat ovládací prvky uživatelského rozhraní do souboru XML nebo k libovolnému zdroji dat CLR.|[Zobrazení dat](../designers/display-data-in-blend.md)|

Další informace o pokročilý design XAML najdete v tématu [vytvoření uživatelského rozhraní pomocí nástroje Blend pro Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md).
