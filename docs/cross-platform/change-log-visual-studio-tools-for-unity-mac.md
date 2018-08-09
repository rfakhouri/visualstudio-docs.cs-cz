---
title: Protokol změn (Visual Studio Tools for Unity, Mac) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 08/06/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 33a6ac54-d997-4308-b5a0-af7387460849
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: f2bea6bca74fa3c97e6501a44f7d9ea950369d6c
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639725"
---
# <a name="change-log-visual-studio-tools-for-unity-mac"></a>Protokol změn (Visual Studio Tools for Unity, Mac)
Protokol změn Visual Studio Tools for Unity.

## <a name="1602"></a>1.6.0.2
 Vydáno 24. července 2018

### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

     -   Alternativní řešení vrácení zpět pro Unity výkonu chyb (jako je Unity oprava tohoto problému).
     
## <a name="1601"></a>1.6.0.1
 Vydáno 10. července 2018

### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

     -   Oprava zabarvení kódu shaderu podporovat.
     
## <a name="1600"></a>1.6.0.0
 Vydáno 26. června 2018

### <a name="bug-fixes"></a>Opravy chyb

-   **Průvodci:**

    -   Oprava překlep OnApplicationFocus zpráva.

-   **Generování projektu:**

     -   Přechodné alternativní řešení pro chyby výkonu Unity: při vytváření projektů do mezipaměti MonoIslands.
     
     -   Nelze převést souboru PDB typu portable mdb zobrazovat při používání nového modulu runtime Unity.
     
## <a name="1502"></a>1.5.0.2
 Vydáno 18. dubna 2018
 
### <a name="new-features"></a>Nové funkce

-   **Integrace:**

    -   Přidání podpory pro základní doplňování kódu shaderu.
    
    -   Přidání podpory pro přepínání komentáře v souborech shaderu.

## <a name="1501"></a>1.5.0.1
 Vydáno 28. března 2018
 
### <a name="new-features"></a>Nové funkce

-   **Integrace:**

    -   Přidání podpory pro další šablony v Průzkumníku projektů Unity.

## <a name="1500"></a>1.5.0.0
 Vydáno 21. březnem 2018
 
### <a name="new-features"></a>Nové funkce

-   **Integrace:**

    -   Přidání podpory pro zjišťování a připojování k aktérů Androidu prostřednictvím USB připojená.

## <a name="1403"></a>1.4.0.3
 Vydané 5. března 2018
 
### <a name="new-features"></a>Nové funkce

-   **Generování projektu:**

    -   Přidání podpory pro nový generátor projektu v Unity 2018.1.

-   **Integrace:**

    -   Možnost přidání panelu pro vyhrazené nastavení.

## <a name="1402"></a>1.4.0.2
 Vydáno 24. ledna 2018
 
### <a name="bug-fixes"></a>Opravy chyb

-   **Generování projektu:**

    -   Detekce Mono opravenou verzi.

-   **Integrace:**

    -   Oprava problémy načasování s 2018.1 a aktivace modulu plug-in.

    -   Oprava upozornění při zjištění nového hráče.

## <a name="1401"></a>1.4.0.1
 Vydáno 23. ledna 2018
 
### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

    -   Klikněte dvakrát na pevnou Rozbalit/sbalit složky na

## <a name="1400"></a>1.4.0.0
 Vydáno 13. prosince 2017
 
### <a name="new-features"></a>Nové funkce

-   **Generování projektu:**

    -   Přidání podpory pro .NET Standard.

### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

    -   Oprava automatické pdb do mdb ladicí symbol převodu.

## <a name="1301"></a>1.3.0.1
 Vydáno 12. prosince 2017
 
### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

    -   Oprava nepřímé volání EditorPrefs.GetBool vliv na okně Inspektor. při pokusu o změnu velikosti pole.

-   **Průvodci:**

    -   Před vložením metoda aktualizujte roslyn kontextu.

## <a name="1300"></a>1.3.0.0
 Vydáno 20. listopadu 2017
 
### <a name="new-features"></a>Nové funkce

-   **Průvodci:**

    -   Přidání průvodce "Unity implementujte zprávu".

    -   Přidání podpory pro nové dokončení rozhraní API v sadě Visual Studio pro Mac 7.4.

## <a name="1200"></a>1.2.0.0
 Vydáno 23. října 2017
 
### <a name="new-features"></a>Nové funkce

-   **Ladicí program:**

    -   Přidání podpory pro soubory symbolů ladění přenosné.

### <a name="bug-fixes"></a>Opravy chyb

-   **Generování projektu:**

    -   Opravili jsme navíc DLL rozšíření chybně přidá k názvu souboru sestavení.

    -   Nesnažte se vynutit příznak AllowAttachedDebuggingOfEditor Unity jako výchozí hodnota je "true".

## <a name="1103"></a>1.1.0.3
 Vydáno 23. října 2017
 
### <a name="new-features"></a>Nové funkce

-   **Generování projektu:**

    -   Přidání podpory pro profil .NET 4.6.

## <a name="1102"></a>1.1.0.2
 Vydáno 8. srpna 2017
 
### <a name="new-features"></a>Nové funkce

-   **Ladicí program:**

    -   Spustit dialogu připojit k procesu, pokud nejste si jisti, jaké Unity pro připojení k.

-   **Generování projektu:**

    -   Vždy povolte přepínač nebezpečné kompilace při použití Unity 5.6.

## <a name="1101"></a>1.1.0.1
 Vydáno 20. července 2017
 
### <a name="new-features"></a>Nové funkce

-   **Integrace:**

    -   Přidání podpory pro lokalizované prostředky.

## <a name="1100"></a>1.1.0.0
 Vydáno 12. července 2017
 
### <a name="new-features"></a>Nové funkce

-   **Integrace:**

    -   Přidání podpory pro připojení k hráčům a editory prostřednictvím připojit k procesu okno.

-   **Generování projektu:**

    -   Pevné odkazy na název sestavení se mcs.rsp soubory.

    -   Přidání podpory pro assembly.json kompilačních jednotek.    

    -   Oprava definuje s úrovní rozhraní API.    

### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

    -   Oprava shaderu chybová zpráva při kompilaci.

## <a name="1001"></a>1.0.0.1
 Vydáno 4. května 2017
 
### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

    -   Oprava aktivní sledování dokumentů s hybridní a běžných projektů.

## <a name="1000"></a>1.0.0.0
 Vydáno 3. května 2017
