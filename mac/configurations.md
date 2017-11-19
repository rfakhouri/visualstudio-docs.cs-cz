---
title: "Principy konfigurací sestavení"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 78107CFA-9308-4293-A92A-9B552A259E15
ms.openlocfilehash: e435418c0c77f1577e9db8ab35d76d6bd54f8447
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="understanding-build-configurations"></a>Principy konfigurací sestavení

## <a name="project-build-configurations"></a>Konfigurace sestavení projektu 

Projekty může mít víc konfigurací a přepínání mezi nimi umožňuje různých výstupy v čase vytvoření buildu. Například pokud použijete konfiguraci ladění, výstup bude obsahovat ladění symboly, což umožňuje ladicí program přeložit názvy funkcí, parametrů nebo proměnné z trasování zásobníku chyb aplikace. Použijete konfiguraci ladění, ale za následek zvýšeným velikost a tak nebude ideální pro aplikaci určených pro distribuci.

Každá platforma bude mít konkrétní konfigurace pro jeho sestavení. Vývoj pro Xamarin.Android bude mít vždy pouze konfiguraci verze nebo verze pro ladění. Xamarin.iOS má další konfigurace. Projekty budou mít pouze novější iOS ladění a vydání konfigurace, ale ty lze nastavit pro všechny nainstalované simulátoru nebo zařízení.

## <a name="solution-configurations"></a>Konfigurace řešení

Konfigurace řešení se podobají konfigurace projektu použít k vytvoření vlastní konfigurace pro celý projekt. Pomocí **konfigurace mapování** v části **sestavení > Konfigurace** položky, můžete přiřadit konfigurace cílového pro každou položku řešení, jak je uvedeno dále:


 ![Možnosti konfigurace mapování](media/projects-and-solutions-image3.png)

Další informace najdete v části [nástroje Configuration Manager](https://www.youtube.com/watch?v=tjSdkqYh5Vg) video od James Montemagno.

## <a name="run-configuration"></a>Spuštění nástroje Konfigurace

V předchozích verzích nástroje Xamarin Studio můžete třeba vybrat možnost nastavte projekt jako **spouštěný projekt**, což je projekt, který je spustit nebo ladit při použití příkazu globální spustit/debug. To se indikován tučné písmo pro název projektu v panelu pro projekt.

V sadě Visual Studio pro Mac, namísto nastavování spouštěný projekt, můžete nastavit _spustit konfigurace_. Spuštění konfigurace jsou uvedeny v rozevíracím seznamu v panelu nástrojů vedle selektor sestavení konfigurace, jak je uvedeno dále:

 ![Spuštění konfigurace rozevíracího seznamu](media/projects-and-solutions-image8.png)

Spuštění konfigurace je sada možností spouštění s názvem a několik konfigurací, které jsou definovány v projektu pro jiné účely. Spuštění konfigurace jsou definovány na úrovni projektu a výchozí automaticky se vytvoří pro každý projekt, spustitelný soubor, i když je možné přidat až potřebné. Některé typy projektů automaticky generovat další spuštění konfigurace. Například může vygenerovat watchOS projekty _konfigurace přehledu a oznámení._ 
 
Konfigurace můžete sdílet s jinými vývojáři (v takovém případě konfigurace bude uložen v souboru .csproj) nebo uchovávají místně (v takovém případě budou uloženy v souboru .uživatel).

### <a name="android-run-configurations"></a>Android spustit konfigurace
 
Spuštění konfigurace pro Android projekty umožňují určit, které aktivity, služby nebo všesměrového vysílání příjemce pro spuštění při spuštění nebo ladění projektu. Můžete předat záměrné doplňující data a nastavte záměrné příznaky mohli otestovat vaše komponenty pro v různých spuštění podmínkách.

Aktivity jinak než `MainLauncher` potřebovat `Exported=true` přidat do atribut aktivity pro ladění na fyzické zařízení nebo definovali záměrné filtry.

## <a name="examples-of-data-that-might-be-included-in-run-configurations"></a>Příklady data, která může být součástí spuštění konfigurace

Následující seznam uvádí některé příklady data, která může být součástí spuštění konfigurace:

* Pravidelné projektové rozhraní .NET
    * Alternativní spuštění aplikace
    * Spustit argumenty
    * Pracovní adresář
    * Proměnné prostředí
    * Možnosti mono runtime (který se má použít, pouze pokud se používá na Mono)
* Projekt pro Android
    * Vstupní bod (aktivity, služby, příjemce)
    * Záměrné argumentů a dat
* projekt pro iOS
    * Režim (normální, načítání na pozadí)
* rozšíření projektu iOS
    * Spuštění aplikace: výchozí nebo vlastní
* WatchKit projektu
    * Režim (přehledu, oznámení)
    * Datová část oznámení
