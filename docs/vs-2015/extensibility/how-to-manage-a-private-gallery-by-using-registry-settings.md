---
title: 'Postupy: Správa privátní galerie s použitím nastavení registru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSIX private galleries, managing
- managing VSIX private galleries
ms.assetid: 86b86442-4293-4cad-9fe2-876eef65f426
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a55b7aa486edfd3775b12dca9d143c2e5f280884
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68204161"
---
# <a name="how-to-manage-a-private-gallery-by-using-registry-settings"></a>Postupy: Správa privátní galerie pomocí nastavení registru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud jste správce nebo vývojáře rozšíření izolovaného prostředí, můžete řídit přístup ke ovládací prvky, šablony a nástroje v Galerii Visual Studio, Galerie ukázek nebo privátní galerie. Chcete-li galerii k dispozici nebo není k dispozici, vytvořte soubor .pkgdef, který popisuje změny registru klíčů a jejich hodnoty.  
  
## <a name="managing-private-galleries"></a>Správa privátní Galerie  
 Můžete vytvořit soubor .pkgdef pro řízení přístupu k Galerie ve více počítačích. Tento soubor musí mít následující formát.  
  
```  
[$RootPath$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) … MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom Feed|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 `Repositories` Klíč odkazuje na galerii má být povolena nebo zakázána. Galerie Visual Studio a Galerie vzorových příkladů použijte následující úložiště identifikátory GUID:  
  
- Galerie Visual Studio: 0F45E408-7995-4375-9485-86B8DB553DC9  
  
- Galerie vzorových příkladů: AEB9CB40-D8E6-4615-B52C-27E307F8506C  
  
  `Disabled` Hodnota je volitelná. Galerie je ve výchozím nastavení povolené.  
  
  `Priority` Hodnota určuje pořadí, ve kterém jsou uvedeny v galeriích v dialogovém okně Možnosti. Galerie Visual Studio má prioritu 10 a Galerie vzorových příkladů má prioritu 20. Spustit privátní galerie s prioritou 100. Pokud několik galeriích mají stejnou hodnotu priority, pořadí, ve kterém jsou uvedeny je dáno hodnoty jejich lokalizované `DisplayName` atributy.  
  
  `Protocol` Hodnota je povinná pro galerie na základě Atom nebo na Sharepointu.  
  
  Buď `DisplayName`, nebo obojí `DisplayNameResourceID` a `DisplayNamePackageGuid`, musí být zadán. Pokud jsou všechny zadané, pak bude `DisplayNameResourceID` a `DisplayNamePackageGuid` pár se používá.  
  
## <a name="disabling-the-visual-studio-gallery-using-a-pkgdef-file"></a>Zakázání Galerie sady Visual Studio pomocí souboru .pkgdef  
 Můžete zakázat Galerie v souboru .pkgdef. Zakáže následující položku Galerie sady Visual Studio:  
  
```  
[$RootPath$\ExtensionManager\Repositories\{0F45E408-7995-4375-9485-86B8DB553DC9}]  
"Disabled"=dword:00000001  
  
```  
  
 Zakáže následující položku Galerie vzorových příkladů:  
  
```  
[$RootPath$\ExtensionManager\Repositories\{AEB9CB40-D8E6-4615-B52C-27E307F8506C}]  
"Disabled"=dword:00000001  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Privátní galerie](../extensibility/private-galleries.md)
