---
title: "Postupy: Přidání závislosti balíčku VSIX | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f6f1e4739922a2d73999b36c0dc66e6069a6d6b
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/29/2017
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Postupy: Přidání závislosti balíčku VSIX

Můžete nastavit nasazení balíčku VSIX, který nainstaluje všechny závislosti, které ještě neexistují na cílovém počítači. K tomu, obsahovat závislosti VSIX source.extension.vsixmanifest souboru.

## <a name="to-add-a-dependency"></a>Chcete-li přidat závislost

1. Otevřete soubor source.extension.vsixmanifest v **návrhu** zobrazení. Přejděte na **závislosti** a klikněte na **nový**.

2. Přidat nainstalované rozšíření: v **přidat nové závislosti** dialogové okno, vyberte **nainstalované rozšíření** a potom u **název**, vyberte v seznamu rozšíření.

3. Chcete-li přidat další VSIX, který není nainstalován:: v **přidat nové závislosti** dialogové okno, vyberte **souboru v systému souborů** a pak použijte **Procházet** tlačítko vyberte VSIX.

## <a name="require-a-specific-visual-studio-release"></a>Vyžadovat určité verze Visual Studio

Pokud toto rozšíření vyžaduje určitou verzi sady Visual Studio 2017, například závisí na funkci vydané v 15.3, můžete zadat číslo sestavení ve vašem VSIX **InstallationTarget**. Verze 15.3 například má počet sestavení '15.0.26730.3'. Můžete zobrazit mapování k sestavení čísla verzí [zde](../install/visual-studio-build-numbers-and-release-dates.md). Všimněte si, že použití číslo verze '15.3, nebude fungovat správně.

Pokud vaše rozšíření vyžaduje 15.3 nebo vyšší, by deklarovat **InstallationTarget verze** jako [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```

VSIXInstaller rozpozná starší verze sady Visual Studio a informovat uživatele, že je vyžadována novější aktualizace.


## <a name="see-also"></a>Viz také

 [Referenční dokumentace schématu 1.0 rozšíření VSIX](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b) [anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md) [rozšíření Příprava nasazení Instalační služby systému Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)