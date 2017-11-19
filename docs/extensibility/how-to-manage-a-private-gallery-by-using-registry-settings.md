---
title: "Postupy: Správa galerie privátní pomocí nastavení registru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX private galleries, managing
- managing VSIX private galleries
ms.assetid: 86b86442-4293-4cad-9fe2-876eef65f426
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c7f9c12cef9b46cc29c4fda6ad74855b69386dc9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-manage-a-private-gallery-by-using-registry-settings"></a>Postupy: Správa galerie privátní pomocí nastavení registru
Pokud jste správce nebo vývojáře rozšířením izolovaném prostředí, můžete řídit přístup na ovládací prvky, šablony a nástroje v Galerii Visual Studia, Galerie ukázek nebo privátní galerie. Chcete-li galerie, k dispozici nebo není k dispozici, vytvořte soubor .pkgdef, který popisuje změny registru klíčů a jejich hodnoty.  
  
## <a name="managing-private-galleries"></a>Správu galerií privátní  
 Můžete vytvořit soubor .pkgdef k řízení přístupu k Galerie na několika počítačích. Tento soubor musí mít následující formát.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom Feed|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 `Repositories` Klíč odkazuje na galerii povolit nebo zakázat. Galerii Visual Studio a ukázky Galerie použijte následující úložiště identifikátory GUID:  
  
-   Galerie sady Visual Studio: 0F45E408-7995-4375-9485-86B8DB553DC9  
  
-   Ukázky galerie: AEB9CB40-D8E6-4615-B52C-27E307F8506C  
  
 `Disabled` Hodnota je volitelná. Galerie je ve výchozím nastavení povolené.  
  
 `Priority` Hodnota určuje pořadí, ve kterém jsou uvedeny Galerie v dialogovém okně Možnosti. Galerie sady Visual Studio má prioritu 10 a galerii ukázky má prioritu 20. Privátní Galerie začínají s prioritou 100. Pokud několik Galerie mají stejnou prioritu, pořadí, ve kterém jsou zobrazeny je určen podle hodnoty jejich lokalizované `DisplayName` atributy.  
  
 `Protocol` Je požadována hodnota pro galerie na základě Atom nebo založený na Sharepointu.  
  
 Buď `DisplayName`, nebo obojí `DisplayNameResourceID` a `DisplayNamePackageGuid`, musí být zadán. Pokud nejsou zadány všechny, pak se `DisplayNameResourceID` a `DisplayNamePackageGuid` pár se používá.  
  
## <a name="disabling-the-visual-studio-gallery-using-a-pkgdef-file"></a>Zakázání Galerii Visual Studio pomocí souboru .pkgdef  
 Galerie v souboru .pkgdef můžete zakázat. Následující položku zakáže Galerii Visual Studio:  
  
```  
[$RootKey$\ExtensionManager\Repositories\{0F45E408-7995-4375-9485-86B8DB553DC9}]  
"Disabled"=dword:00000001  
  
```  
  
 Následující položku zakáže galerii ukázky:  
  
```  
[$RootKey$\ExtensionManager\Repositories\{AEB9CB40-D8E6-4615-B52C-27E307F8506C}]  
"Disabled"=dword:00000001  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Privátní Galerie](../extensibility/private-galleries.md)