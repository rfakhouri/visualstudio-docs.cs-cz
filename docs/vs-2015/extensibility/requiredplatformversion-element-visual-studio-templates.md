---
title: Requiredplatformversion – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2e5ba8cfef6674b5603cf03c73619f686338af3c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68159284"
---
# <a name="requiredplatformversion-element-visual-studio-templates"></a>RequiredPlatformVersion – element (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
