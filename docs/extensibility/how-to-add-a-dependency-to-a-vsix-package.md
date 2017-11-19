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
ms.openlocfilehash: d3f3b54e19d8418f35a733b73ea0616b53bd42ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Postupy: Přidání závislosti balíčku VSIX
Můžete nastavit nasazení balíčku VSIX, který nainstaluje všechny závislosti, které ještě neexistují na cílovém počítači. K tomu, obsahovat závislosti VSIX source.extension.vsixmanifest souboru.  
  
#### <a name="to-add-a-dependency"></a>Chcete-li přidat závislost  
  
1.  Otevřete soubor source.extension.vsixmanifest v **návrhu** zobrazení. Přejděte na **závislosti** a klikněte na **nový**.  
  
2.  Přidat nainstalované rozšíření: v **přidat nové závislosti** dialogové okno, vyberte **nainstalované rozšíření** a potom u **název**, vyberte v seznamu rozšíření.  
  
3.  Chcete-li přidat další VSIX, který není nainstalován:: v **přidat nové závislosti** dialogové okno, vyberte **souboru v systému souborů** a pak použijte **Procházet** tlačítko vyberte VSIX.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu 1.0 rozšíření VSIX](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)   
 [Příprava rozšíření pro nasazení Instalační služby systému Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)