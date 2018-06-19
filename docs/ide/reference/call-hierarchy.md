---
title: Najít volání metody
ms.date: 05/18/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.CallHierarchy
helpviewer_keywords:
- Call Hierarchy
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 52fdaf277d8c20801c5d48d90de472d24ab88bda
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448347"
---
# <a name="view-call-hierarchy"></a>Zobrazení hierarchie volání

Zobrazení hierarchie volání kódu, můžete přejít všechna volání do a někdy z vybrané metoda, vlastnost nebo konstruktor. Díky tomu můžete lépe pochopit tok kódu a vyhodnotit vliv změn kódu. Můžete zkontrolovat několik úrovní kódu zobrazíte komplexní řetězy volání metod a další vstupní body do kódu. Umožňuje prozkoumat všechny možné provádění cesty.

V sadě Visual Studio můžete zobrazit hierarchii volání v době návrhu. To znamená, že nemáte k nastavení boru přerušení a spuštění ladicího programu zobrazíte zásobníku volání běhu.

## <a name="use-the-call-hierarchy-window"></a>Použití okna hierarchie volání

Chcete-li zobrazit **hierarchie volání** okna, klikněte pravým tlačítkem myši na název metoda, vlastnost nebo volání konstruktoru editoru kódu a potom vyberte **zobrazení hierarchie volání**.

Název člena je zobrazen v podokně zobrazení stromu v **hierarchie volání** okno. Pokud rozbalíte uzlu člen **volání do** *název člena*a pro jazyk C++, **volání z** *název člena*, zobrazí podřízených uzlů.

Kód jazyka C++ uvidíte volání do a ze člena:

![Hierarchie volání pro kódu C++ v sadě Visual Studio](media/call-hierarchy-cpp.png)

Pro C# a kód jazyka Visual Basic můžete zjistit počet volání na člena, ale není volání z:

![Hierarchie volání pro kód C# v sadě Visual Studio](media/call-hierarchy-csharp.png)

- Pokud rozbalíte **volání do** uzlu, všechny členy, že se zobrazují volání vybraného člena.

- Pro jazyk C++, f rozbalíte **volání z** zobrazují v uzlu všechny členy, kteří jsou volány vybraného člena.

Můžete rozbalit každý člen volání zobrazíte jeho **volání do**a pro jazyk C++, **volání z** uzlů. To umožňuje přejděte do zásobníku volající, jak je znázorněno na následujícím obrázku:

![Hierarchie volání – okno s více úrovněmi rozšířit](media/call-hierarchy-csharp-expanded.png)

Pro členy, které jsou definovány jako virtuální nebo abstraktní **název metody přepsání** uzel se objeví. Pro členy rozhraní **název metody implementuje** uzel se objeví. Tyto uzly rozšíření se zobrazí na stejné úrovni jako **volání do** a **volání z** uzlů.

**Obor vyhledávání** na panelu nástrojů obsahuje možnosti pro **Moje řešení**, **aktuálního projektu**, a **aktuálním dokumentu**.

Když vyberete podřízený člen v **hierarchie volání** podokno se stromovým zobrazením:

- **Hierarchie volání** podokně podrobností se zobrazí všechny řádky kódu, ve kterém je daný člen podřízené volána z nadřazeného člena.

- **Definice kódu** okno, pokud otevřené, zobrazí kód pro vybraného člena (C++ pouze). Další informace o tomto okně najdete v tématu [zobrazení struktury kódu](../../ide/viewing-the-structure-of-code.md).

> [!NOTE]
> **Hierarchie volání** funkce nevyhledá metoda odkazy skupiny, který zahrnuje míst, kde se přidá jako obslužné rutiny události metodu, nebo je přiřazená delegáta. Pokud chcete najít všechny odkazy na metodu, můžete použít **najít všechny odkazy** příkaz.

## <a name="shortcut-menu-items"></a>Položky místní nabídky

Následující tabulka popisuje několik možnosti místní nabídky, které jsou k dispozici, když kliknete pravým tlačítkem na uzel v podokně zobrazení stromu.

|Položky kontextové nabídky|Popis|
|-----------------------|-----------------|
|**Přidat jako nový kořen**|Přidá vybraný uzel do podokna zobrazení stromu jako nový kořenový uzel. To umožňuje zaměřit se na konkrétní podstrom vaši pozornost.|
|**Odebrat kořenové**|Odebere vybraného kořenového uzlu z podokna zobrazení stromu. Tato možnost je dostupná pouze z kořenového uzlu.<br /><br /> Můžete také **odebrat kořenové** tlačítka panelu nástrojů k odebrání vybrané kořenového uzlu.|
|**Přechod na definici**|Spustí příkaz Přejít k definici na vybraný uzel. Umožňuje přejít k původní definici pro volání člena nebo definicí proměnné.<br /><br /> Spustit příkaz Přejít k definici, můžete také dvakrát klikněte na vybraný uzel nebo stiskněte klávesu F12 na vybraný uzel.|
|**Najít všechny odkazy**|Spustí příkaz Najít všechny odkazy na vybraný uzel. To tento odkaz třída nebo člen vyhledá všechny řádky kódu v projektu.<br /><br /> SHIFT + F12 také můžete spustit příkaz Najít všechny odkazy na vybraný uzel.|
|**Kopírování**|Zkopíruje obsah vybraného uzlu (ale ne jeho podřízené uzly).|
|**Aktualizace**|Sbalí vybraného uzlu tak, aby znovu rozšíření se zobrazí aktuální informace.|