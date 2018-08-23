---
title: Requiredplatformversion – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5fb35bfefeb7722c3ec488a1f9caf63cd49202dd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670344"
---
# <a name="requiredplatformversion-element-visual-studio-templates"></a>RequiredPlatformVersion – element (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [requiredplatformversion – Element (šablony sady Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/requiredplatformversion-element-visual-studio-templates).  
  
Určuje minimální verzi operačního systému, šablonu projektu vyžaduje fungovat správně. Tento element slouží k pro šablony projektů, které vytvářejí [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace.  
  
 `RequiredPlatformVersion` Se porovnává hodnotu přímo s verzí operačního systému. Pokud `RequiredPlatformVersion` je vyšší než verze operačního systému, šablonu se nezobrazují v **nový projekt** dialogové okno. Chcete-li zadat šablonu pro [!INCLUDE[win8](../includes/win8-md.md)] nebo vyšší, nastavte `RequiredPlatformVersion` k 6.2.0. Chcete-li zadat šablonu pro [!INCLUDE[win81](../includes/win81-md.md)] nebo vyšší, nastavte requiredplatformversion – na 6.3.0.  
  
 Šablony, které určují `RequiredPlatformVersion`= 8 musí být kompatibilní s předchozím zákazníka [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] šablony.  
  
 VSTemplate  
TemplateData  
... Targetplatformname –  
RequiredPlatformVersion  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<RequiredPlatformVersion> OperatingSystem </RequiredPlatformVersion>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Žádné  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplatePlatformName](../extensibility/templatedata-element-visual-studio-templates.md)|Určuje platformu, která šablona cíle projektu.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
## <a name="remarks"></a>Poznámky  
 Tento text určuje minimální verzi operačního systému vyžadované šablonou.  
  
## <a name="example"></a>Příklad  
 Tento příklad určuje, že projekt cílí šablony [!INCLUDE[win8](../includes/win8-md.md)] nebo novější.  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0"    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <TargetPlatformName>Windows</TargetPlatformName>  
            <RequiredPlatformVersion>6.3.0</RequiredPlatformVersion>  
  
    </TemplateData>  
    <TemplateContent>  
  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Targetplatformname – Element (šablony sady Visual Studio)](../extensibility/targetplatformname-element-visual-studio-templates.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)

