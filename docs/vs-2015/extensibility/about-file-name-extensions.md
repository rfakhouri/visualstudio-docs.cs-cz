---
title: O přípony názvů souborů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 866a30279ca2c79f4a490a040f76bc3a86c6a6e1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54759107"
---
# <a name="about-file-name-extensions"></a>Přípony názvů souborů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Když si zaregistrujete příponu souboru sady VSPackage, přiřaďte ji k verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. To je důležité, pokud více než jednu verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] je nainstalovaná na počítači.  
  
 Přípony souborů pro balíčky VSPackages jsou registrována pod klíč HKEY_CLASSES_ROOT s výchozí hodnotou, která odkazuje na související programový identifikátor (ProgID).  
  
 Následuje příklad registračních informací pro příponu souboru .vcproj:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 Soubory přidružené k [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] musí mít ProgID označené verzí, jako například `VisualStudio.vcproj.8.0`, aby vedle sebe instalacích udržovat přidružení přípony souboru mezi verzemi tohoto produktu. Identifikátor ProgID specifické pro verzi také umožňuje používat standardní příkazy, jako třeba otevřít, upravit a tak dále, bez obav přepsat nebo přepsání jiné aplikace nebo verzí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 V některých případech by neměla změnit ProgID spojené s příponou souboru. Například ProgID pro příponu souboru HTM (progid = htmlfile) je obtížné nakódovat v řadě míst v operačním systému a je široce známé a používat v přidružení se soubory .htm a .html.  
  
## <a name="see-also"></a>Viz také  
 [Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [Určení popisovačů souborů pro přípony názvů souborů](../extensibility/specifying-file-handlers-for-file-name-extensions.md)
