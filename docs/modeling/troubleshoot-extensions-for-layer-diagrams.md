---
title: Řešení potíží s rozšířeními pro diagramy závislostí
ms.date: 11/04/2016
ms.topic: troubleshooting
helpviewer_keywords:
- dependency diagrams, extension errors
- dependency diagrams, troubleshooting extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: b56ccd587df4a830eab5bee000cafcc02b0031e8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949368"
---
# <a name="troubleshoot-extensions-for-dependency-diagrams"></a>Řešení potíží s rozšířeními pro diagramy závislostí

Toto téma nabízí některé problémy, které se můžete setkat při vytváření vrstvy rozšířeních modelu.

## <a name="when-i-press-f5-to-debug-my-extension-my-commands-gesture-handlers-validation-extensions-or-custom-properties-do-not-appear-on-dependency-diagrams-in-the-experimental-instance-of-includevsprvscode-qualityincludesvsprvsmdmd"></a>Po stisknutí klávesy F5 k ladění Moje rozšíření, příkazy, obslužné rutiny gesto, ověření rozšíření nebo vlastní vlastnosti se nezobrazí v diagramech závislostí v experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]

1.  Otevřete řešení rozšíření v experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]a na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.

2.  Stiskněte klávesu **F5** nebo **CTRL + F5** zahájíte experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Otevřít diagram závislostí a testování rozšíření.

 V případě potřeby, pokračujte v dalším postupu.

## <a name="an-old-version-of-my-extension-runs"></a>Starší verzi rozšíření my spustí.

1.  Ujistěte se, že není žádná instance experimentální [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží.

2.  Odstraňte následující složku: %LocalAppData%\Microsoft\VisualStudio\\\ComponentModelCache [verze]

    > [!NOTE]
    > % LocalAppData % je obvykle *DriveName*: \Users\\*uživatelské jméno*\AppData\Local.

 V případě potřeby, pokračujte v dalším postupu.

## <a name="an-old-version-of-my-validation-results-appears-or-my-validation-method-is-not-called"></a>Stará verze architektury Moje výsledky ověření se zobrazí, nebo Moje ověření metoda není volána.

1.  V experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**. Zruší výsledky uložené v mezipaměti předchozí analýzy ověření.

2.  Ujistěte se, že vrstvy v modelu jsou spojeny s elementy kódu a že je alespoň jeden odkaz závislostí v modelu. Ověření není vyvolána, pokud není nic k ověření.

3.  Regulární zarážky nemusí fungovat v metodu ověření, protože běží jako samostatný proces. Je třeba vložit volání `System.Diagnostics.Debugger.Launch()` Pokud chcete procházet metodu.

4.  V **source.extension.vsixmanifest** ve vašem projektu ověření vrstvy, ujistěte se, přidali i **Komponenta MEF** položky a **vlastní typ rozšíření** položku **Obsahu**.

## <a name="see-also"></a>Viz také

- [Rozšíření diagramů závislostí](../modeling/extend-layer-diagrams.md)
