---
title: 'Postupy: Přidání závislosti k balíčku VSIX | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ee6ebeb776e6aa85d5fba200ac357a7375fa2b99
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341050"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Postupy: Přidání závislosti k balíčku VSIX

Můžete nastavit nasazení balíčku VSIX, který instaluje všechny závislosti, které ještě nejsou k dispozici na cílovém počítači. K tomu patří závislosti VSIX a *source.extension.vsixmanifest* souboru.

## <a name="to-add-a-dependency"></a>Chcete-li přidat závislost

1. Otevřít *source.extension.vsixmanifest* soubor **návrhu** zobrazení. Přejděte **závislosti** kartě a klikněte na tlačítko **nový**.

2. Přidání nainstalovaných rozšíření: v **přidat novou závislost** dialogovém okně vyberte **nainstalované rozšíření** a potom v **název**, vyberte v seznamu rozšíření.

3. Chcete-li přidat další VSIX, který není nainstalován: v **přidat novou závislost** dialogovém okně vyberte **souboru v systému souborů** a pak pomocí **Procházet** tlačítko a vyberte rozšíření VSIX.

## <a name="require-a-specific-visual-studio-release"></a>Vyžadovat konkrétní verzi sady Visual Studio

Pokud rozšíření vyžaduje určitou verzi sady Visual Studio 2017, například to závisí na nová funkce od verze 15.3, můžete zadat číslo sestavení do VSIX **InstallationTarget**. Například verze 15.3 má sestavení počet "15.0.26730.3". Zobrazí se mapování verzí čísla sestavení [tady](../install/visual-studio-build-numbers-and-release-dates.md). Všimněte si, že pomocí čísla verze "15.3" nebudou fungovat správně.

Pokud rozšíření vyžaduje 15.3 nebo novější, by deklarovat **InstallationTarget verze** jako [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```

VSIXInstaller zjistí starší verze sady Visual Studio a informovat uživatele, že je vyžadována novější aktualizace.

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace schématu 1.0 rozšíření VSIX](https://msdn.microsoft.com/library/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
- [Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)
- [Příprava rozšíření pro nasazení Instalační služby systému Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)
