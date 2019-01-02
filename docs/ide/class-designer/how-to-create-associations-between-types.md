---
title: 'Postupy: Vytvoření asociací mezi typy (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.associationline
helpviewer_keywords:
- types [Visual Studio], associations
- association lines, defining (Class Designer)
- defining association lines (Class Designer)
- associations, types
- association lines
ms.assetid: adccb9c8-2f8a-4086-9fa9-f70f99fb6e00
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77f957e112835c138a84accbdc7070f1217fc963
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916598"
---
# <a name="how-to-create-associations-between-types-in-class-designer"></a>Postupy: Vytvoření asociací mezi typy v Návrháři tříd

Přidružení řádků **návrhář tříd** ukazují, jak jsou související třídy v diagramu. Asociační čára představuje třídu, která je typem vlastnosti nebo pole jiné třídy ve vašem projektu. Asociační čáry obecně slouží ke znázornění nejdůležitějších vztahů mezi třídami v projektu.

Ačkoli můžete zobrazit všechna pole a vlastnosti jako přidružení, je vhodnější jako přidružení zobrazit pouze důležité členy nebo přidružení v závislosti na tom, co chcete v diagramu zdůraznit. (Můžete zobrazit méně důležité členy jako běžné členy nebo je zcela skrýt.)

> [!NOTE]
> **Návrhář tříd** podporuje pouze jednosměrná přidružení.

## <a name="to-define-an-association-line-in-the-class-diagram"></a>Definování asociační čáry v diagramu tříd

1. Na panelu nástrojů v rámci **návrhář tříd**vyberte **přidružení**.

2. Nakreslete čáru mezi dvěma tvary, které chcete propojit pomocí přidružení.

     V první třídě se vytvoří nová vlastnost. Tato vlastnost se zobrazí jako asociační čára (nikoli jako vlastnost v prostoru ve tvaru) s výchozím názvem. Její typ je tvar, na který asociační čára ukazuje.

## <a name="to-change-the-name-of-an-association"></a>Změna názvu přidružení

Na ploše diagramu klikněte na popisek asociační linky a upravte jej.

Případně postupujte podle těchto kroků:

1. Vyberte obrazec, který obsahuje vlastnost zobrazenou jako přidružení.

   Tvar získá fokus a jeho členy se zobrazí v **podrobností třídy** a **vlastnosti** systému windows.

2. Buď **podrobností třídy** nebo **vlastnosti** okna, upravte pole názvu pro tuto vlastnost a stisknutím klávesy **Enter**.

   Název se aktualizuje v **podrobností třídy** řádek, na okno přidružení, **vlastnosti** okna a v kódu.

## <a name="see-also"></a>Viz také:

- [Postupy: Změna mezi zápisem člena a zápisem asociace](how-to-change-between-member-notation-and-association-notation.md)
