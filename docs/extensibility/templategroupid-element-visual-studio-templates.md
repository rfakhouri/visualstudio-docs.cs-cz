---
title: Templategroupid – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateGroupID
helpviewer_keywords:
- TemplateGroupID element [Visual Studio Templates]
- <TemplateGroupID> element [Visual Studio Templates]
ms.assetid: bce7b49a-90bc-4691-aff3-a87e209f6d83
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 68e89b0211c64dcee61507afc15c50bd8e5e85d2
ms.sourcegitcommit: 35bebf794f528d73d82602e096fd97d7b8f82c25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/18/2018
ms.locfileid: "53560648"
---
# <a name="templategroupid-element-visual-studio-templates"></a>TemplateGroupID – element (šablony sady Visual Studio)
Určuje, jaký typ projektu šablony položek se zobrazí. Tento element je důležité, když [ShowByDefault (šablony sady Visual Studio)](../extensibility/showbydefault-visual-studio-templates.md) je nastavena na `false`. Když [ShowByDefault (šablony sady Visual Studio)](../extensibility/showbydefault-visual-studio-templates.md) je nastavena na `true`, bude k dispozici ve všech typech projektů, šablony položky.  
  
 \<Vstemplate – >  
 \<TemplateData >  
 \<Templategroupid – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<TemplateGroupID> ... </TemplateGroupID>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateData –](../extensibility/templatedata-element-visual-studio-templates.md)|Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Text určuje identifikátor pro kategorii šablony položek.  
  
## <a name="remarks"></a>Poznámky  
 `TemplateGroupID` představuje prvek.  
  
 Hodnota `TemplateGroupID` element se používá spolu s registrace systému projektu (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<číslo verze >* \Projects\\) do šablony filtrů, které se zobrazují v **přidat novou položku** dialogové okno.  
  
|Hodnota Visual C++|Význam|  
|------------------------|-------------|  
|Nativní VC|Použít u nativních projektů. Také výchozí Pokud nelze určit typ projektu.|  
|Spravované VC|Použít pro spravované (/ clr) projekty|  
|VC – Windows|Používá pro všechny projekty, které cílí na platformu windows (nativní a spravovaná/úložiště)|  
|WinRT. nativní UAP|Používá pro projekty pro Windows 10 store|  
|Nativní CodeSharing|Používá pro projekty sdílené položky|  
|WinRT. nativní 6.3|Používá pro projekty pro Windows 8.1 Store|  
|WinRT nativní telefonní 6.3|Používá pro projekty pro Windows Phone 8.1|  
|Nativní WinRT|Používá pro projekty Windows Store 8.0|  
|VC Android|Použít pro projekty pro Android|  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)