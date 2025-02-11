---
title: 'Postupy: Export textury s Přednásobeným alfa | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 05348afa-f079-4f53-a05b-ecd91d13adab
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 61a53d8fca979fce04113aeb963e8cae94a49137
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68159433"
---
# <a name="how-to-export-a-texture-that-has-premultiplied-alpha"></a>Postupy: Export textury s přednásobenou hodnotou alfa
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Kanál s obsahem obrazu může generovat vynásobené alfa textury ze zdrojového obrazu. To může být jednodušší použít a robustnější než textury, které neobsahují předem vynásobené hodnoty alfa.  
  
 Tento dokument vysvětluje tyto činnosti:  
  
- Konfigurace zdrojového obrazu pro zpracování obsahu kanálu obrázku.  
  
- Konfigurace obsahu kanálu obrázku ke generování předem vynásobených hodnot alfa.  
  
## <a name="premultiplied-alpha"></a>Předem vynásobený prvek alfa  
 Předem vynásobený prvek alfa nabízí několik výhod oproti konvenčním, předem alfa, protože lépe představuje skutečných interakci světla s fyzickými materiály oddělením podílu barvy texelu (barvy, který přidá do scény) z jeho průsvitnosti (podíl základní barvy, která umožní průnik částka). Některé výhody použití předem vynásobených hodnot alfa jsou:  
  
- Prolnutí s předem vynásobených hodnot alfa je asociativní operace; Výsledek prolnutí více průhledných textur je stejný, bez ohledu na pořadí, ve kterém jsou textury prolnuty.  
  
- Vzhledem k asociativnímu charakteru prolnutí s předem vynásobených hodnot alfa je vícenásobné vykreslení s více průchody průsvitných objektů zjednodušeno.  
  
- Pomocí předem vynásobené hodnoty alfa čiré aditivní prolnutí (podle nastavení alfa nula) i lineárně interpolované prolnutí lze dosáhnout současně. Například v systému částic směsi částic ohně přeměnit na průsvitné částice kouře, které jsou prolnuty pomocí lineární interpolace. Bez předem vynásobené hodnoty alfa je třeba nakreslit částice ohně odděleně od kouřových částic a měnit stav vykreslení mezi voláními výkresu.  
  
- Textury, které používají předem vynásobenou hodnotu alpha mají vyšší kvalitu než ty, které ji nemají komprese a nevykazují zabarvené hrany – nebo "halo efekt", který může být výsledkem prolnutí textur, které nepoužívají vynásobenou hodnotu alpha.  
  
#### <a name="to-create-a-texture-that-uses-premultiplied-alpha"></a>Vytvoření textury, která používá předem vynásobené hodnoty alfa  
  
1. Začněte základní texturou. Načtěte stávající obrazový soubor nebo jej vytvořte podle pokynů v [jak: Vytvoření základní textury](../designers/how-to-create-a-basic-texture.md).  
  
2. Nakonfigurujte soubor textury tak, aby byl zpracován kanálem obsahu obrázku. V **Průzkumníka řešení**, otevřete místní nabídku pro soubor textury a klikněte na tlačítko **vlastnosti**. Na **vlastnosti konfigurace**, **Obecné** nastavte **typ položky** vlastnost **kanál obsahu obrazu**. Ujistěte se, že **obsahu** je nastavena na **Ano** a **vyloučit ze sestavení** je nastavena na **ne**a klikněte na tlačítko  **Použít** tlačítko. **Kanál obsahu obrazu** se zobrazí stránka pro konfiguraci vlastností.  
  
3. Nakonfigurujte kanál obsahu obrázku ke generování předem vynásobených hodnot alfa. Na **vlastnosti konfigurace**, **kanál obsahu obrazu**, **Obecné** nastavte **převést na formát přednásobené alfa** Vlastnost **Ano (/ generatepremultipliedalpha)** .  
  
4. Zvolte **OK** tlačítko.  
  
   Při sestavování projektu kanál obsahu obrazu převede zdrojový obraz z pracovního formátu na výstupní formát, který jste zadali – patří sem převod obrázku na předem vynásobený formát alfa – a výsledek je zkopírován do výstupu projektu adresář.
