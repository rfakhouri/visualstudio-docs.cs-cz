---
title: '&lt;compatibleFrameworks&gt; – Element (ClickOnce – nasazení) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d406ecf058bf1c570b57ed8f50815cc3d9378cbe
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt; – Element (ClickOnce – nasazení)
Určuje verzi rozhraní .NET Framework, kde můžete tuto aplikaci nainstalovat a spustit.  
  
> [!NOTE]
>  [MageUI.exe](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client) nepodporuje `compatibleFrameworks` element při ukládání manifest aplikace, která již byla podepsána pomocí certifikátu [MageUI.exe](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Místo toho musíte použít [Mage.exe](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `compatibleFrameworks` Prvek je nutný pro manifesty nasazení cílených [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] runtime poskytované [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] nebo novější. `compatibleFrameworks` Element obsahuje jeden nebo více `framework` elementy, které určují verze rozhraní .NET Framework, na kterých může tato aplikace spustit. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Runtime bude v prvním spuštění aplikace k dispozici `framework` v tomto seznamu.  
  
 Následující tabulka uvádí atribut, `compatibleFrameworks` element podporuje.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`S``upportUrl`|Volitelné. Určuje adresu URL, kde si můžete stáhnout upřednostňované kompatibilní verze rozhraní .NET Framework.|  
  
## <a name="framework"></a>rozhraní  
 Požadováno. Následující tabulka obsahuje seznam atributy, `framework` element podporuje.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`targetVersion`|Požadováno. Určuje číslo verze cílového rozhraní .NET Framework.|  
|`profile`|Požadováno. Určuje profil cílového rozhraní .NET Framework.|  
|`supportedRuntime`|Požadováno. Určuje číslo verze modulu runtime přidružený cílové rozhraní .NET Framework.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `compatibleFrameworks` element v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení. Toto nasazení můžete spustit na [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]. Můžete spustit také na [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] protože je nadmnožinou [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].  
  
```  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)