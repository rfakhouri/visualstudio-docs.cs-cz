---
title: Requiredplatformversion – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 35a8dc6fa57dbe88ce1e30e9be58105f28fe5641
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="requiredplatformversion-element-visual-studio-templates"></a>RequiredPlatformVersion – element (šablony sady Visual Studio)
Určuje minimální verzi operačního systému, který v šabloně projektů vyžaduje, aby správně fungovat. Tento element se používá k pro šablony projektů, které vytvářejí [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace.  
  
 `RequiredPlatformVersion` Hodnota se porovná přímo s verzí operačního systému. Pokud `RequiredPlatformVersion` je vyšší než verze operačního systému v šabloně nezobrazí **nový projekt** dialogové okno. Chcete-li určit šablonu pro [!INCLUDE[win8](../debugger/includes/win8_md.md)] nebo vyšší, můžete nastavit `RequiredPlatformVersion` k 6.2.0. Chcete-li určit šablonu pro [!INCLUDE[win81](../debugger/includes/win81_md.md)] nebo vyšší, můžete nastavit requiredplatformversion – k 6.3.0.  
  
 Šablony, které určují `RequiredPlatformVersion`= 8 jsou kompatibilní s předchozím zákazníka [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] šablony.  
  
 VSTemplate  
TemplateData  
..... Targetplatformname –  
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
 Tento text se určuje minimální verzi operačního systému vyžadované šablonou.  
  
## <a name="example"></a>Příklad  
 Tento příklad určuje, že šablona cíle projektu [!INCLUDE[win8](../debugger/includes/win8_md.md)] nebo novější.  
  
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