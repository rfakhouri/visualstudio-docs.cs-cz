---
title: 'Postupy: Povolení a zákaz úplné analýzy řešení pro spravovaný kód'
ms.date: 03/23/2018
ms.topic: conceptual
helpviewer_keywords:
- full solution analysis
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- dotnet
ms.openlocfilehash: ffda04828789a591c0e6dca35ef391fe6b8556d7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55035469"
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>Postupy: Povolení a zákaz úplné analýzy řešení pro spravovaný kód

*Úplné analýzy řešení* je funkce sady Visual Studio, která vám umožní zobrazit problémy s analýzou kódu pouze ve Vizuálu otevřete C# nebo Visual Basic souborů ve vašem řešení, nebo také v souborů s kódy, které jsou uzavřeny. Ve výchozím nastavení, je úplné analýzy řešení *povolené* v jazyce Visual Basic a *zakázané* vizuálu C#.

Může být užitečné zjistit všechny problémy ve všech souborech, ale může také působit rušivě. Pokud vaše řešení je moc velká, nebo má mnoho souborů je Visual Studio může zpomalit. Pokud chcete omezit počet problémů zobrazí a zlepšení výkonu sady Visual Studio, můžete zakázat úplné analýzy řešení. V případě potřeby můžete snadno znovu povolit tuto funkci.

## <a name="to-toggle-full-solution-analysis"></a>Chcete-li přepnout úplné analýzy řešení

1. Chcete-li otevřít **možnosti** dialogové okno, v panelu nabídek v sadě Visual Studio zvolte **nástroje** > **možnosti**.

1. V **možnosti** dialogového okna zvolte **textový Editor**  >  **C#** nebo **základní**  >  **Advanced**.

1. Vyberte **povolení úplné analýzy řešení** zaškrtávací políčko pro povolení úplné analýzy řešení, nebo zrušte zaškrtnutí políčka pro jeho zakázání. Zvolte **OK** po dokončení.

    ![Povolte úplné řešení analýzy zaškrtávací políčko.](../code-quality/media/options-enable-full-solution-analysis.png)

## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>Výsledky povolení a zakázání úplné analýzy řešení

Na následujícím snímku obrazovky vidíte výsledky při úplné analýzy řešení je povolené. Všechny chyby a problémy s analýzou kódu v *všechny* souborů v řešení se zobrazí, bez ohledu na to, zda jsou dané soubory otevřeny nebo ne.

![Úplná analýza řešení povolené.](../code-quality/media/fsa_enabled.png)

Následující snímek obrazovky ukazuje výsledky ze stejného řešení po zakázání úplné analýzy řešení. Pouze chyby a problémy s analýzou kódu v souborech otevřít řešení se zobrazí v **seznam chyb**.

![Úplné analýzy řešení zakázáno.](../code-quality/media/fsa_disabled.png)

## <a name="automatically-disable-full-solution-analysis"></a>Automaticky zákaz úplné analýzy řešení

Pokud aplikace Visual Studio zjistí, že 200 MB nebo méně paměti systému, je k dispozici, se automaticky zakáže úplné analýzy řešení (a některé další funkce) Pokud je povolené. V tomto případě se zobrazí výstraha oznamující, že Visual Studio zakázal některé funkce. Tlačítko umožňuje znovu povolit úplné analýzy řešení, pokud chcete.

![Upozornění text pozastavení úplné analýzy řešení](../code-quality/media/fsa_alert.png)