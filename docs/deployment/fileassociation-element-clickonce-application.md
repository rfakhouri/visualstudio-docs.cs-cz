---
title: '&lt;fileAssociation&gt; – Element (aplikace ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <fileAssociation> element [ClickOnce application manifest]
- manifests [ClickOnce], fileAssociation element
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 4da80f852526afa4692b7ecd6eefea3cc3c3de7e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltfileassociationgt-element-clickonce-application"></a>&lt;fileAssociation&gt; – Element (ClickOnce aplikace)
Určuje příponu souboru, který se má přidružit aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `fileAssociation` Prvek je volitelný. Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`extension`|Požadováno. Přípona souboru, který chcete přidružit k aplikaci.|  
|`description`|Požadováno. Popis typu souboru pro použití v prostředí.|  
|`progid`|Požadováno. Název, který jedinečně identifikující typ souboru.|  
|`defaultIcon`|Požadováno. Určuje ikonu můžete použít pro soubory s touto příponou. Soubor ikony musí být určena pomocí [ \<soubor > Element](../deployment/file-element-clickonce-application.md) v rámci [ \<sestavení > Element](../deployment/assembly-element-clickonce-application.md) obsahující tohoto elementu.|  
  
## <a name="remarks"></a>Poznámky  
 Tento element musí obsahovat odkaz na obor názvů XML pro "urn: schémata-microsoft-com:clickonce.v1". Pokud `<fileAssociation>` element se používá, musí být zadán po `<application>` v nadřazeném prvku [ \<sestavení > Element](../deployment/assembly-element-clickonce-application.md).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nepřepíše existující přidružení souborů. Aplikace ClickOnce však můžete přepsat přípona souboru pro aktuálního uživatele. Po odinstalaci aplikace ClickOnce ClickOnce odstraní přidružení souborů pro uživatele a znovu je aktivní přidružení počítačů.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `fileAssociation` prvky v aplikaci manifest pro textový editor aplikace nasazené pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Tento příklad kódu obsahuje také [ \<soubor > Element](../deployment/file-element-clickonce-application.md) požadavku `defaultIcon` atribut.  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest aplikace ](../deployment/clickonce-application-manifest.md)