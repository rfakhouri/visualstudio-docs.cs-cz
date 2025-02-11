---
title: Registrace služeb | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- services, registering
ms.assetid: c4ebac40-0374-4dda-948e-06fdda0e9c81
caps.latest.revision: 8
manager: jillfra
ms.openlocfilehash: 64f2afa6e853978e919e466f91475bed1e8d698c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62971287"
---
# <a name="registering-services"></a>Registrace služeb
Pro podporu načítání na vyžádání, zaregistrujte poskytovatele služeb jeho služeb global services s [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 Během vývoje, poskytovatelům spravovaných služeb registraci služby a služby přepsání přidávání atributů do zdrojového kódu pro balíčky a následným sestavením balíčky [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] integrovaného vývojového prostředí. Toto řešení běží nástroj RegPkg.exe výsledné sestavení registraci balíčku a příprava pro nasazení. Další informace najdete v tématu [jak: Zaregistrovat službu](../misc/how-to-register-a-service.md).  
  
 Nespravované poskytovatelé musíte zaregistrovat služby poskytují [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ve službách části nebo službu přepíše část systémového registru. Následující fragment souboru .reg ukazuje, jak může služba SVsTextManager, zaregistrovaný:  
  
```  
[HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\<version number>\Services\{F5E7E71D-1401-11d1-883B-0000F87579D2}]  
@="{F5E7E720-1401-11d1-883B-0000F87579D2}"  
"Name"="SVsTextManager"  
```  
  
 V příkladu výše uvedené číslo verze je verze [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], jako jsou 7.1 nebo 8.0, klíč {F5E7E71D-1401-11d1-883B-0000F87579D2} je identifikátor služby (SID) služby, SVsTextManager a {výchozí hodnotu F5E7E720-1401-11D1-883B-0000F87579D2} je balíček GUID textový správce balíčku VSPackage, která poskytuje služby.  
  
## <a name="remote-services-and-background-threads"></a>Vzdálené služby a vláken na pozadí  
 Služby, které poskytnete nejsou automaticky k dispozici, vzdáleně a vláken na pozadí. Aby byly k dispozici, musíte sestavit a zaregistrovat knihovnu typů.  
  
 Z nespravovaného kódu, který používá Visual Studio knihovny (VSL) můžete zaregistrovat knihovna typů tímto způsobem:  
  
```  
#define VSL_REGISTER_TYPE_LIB TRUE  
#include <VSLPackageDllEntryPoints.cpp>  
```  
  
 Ze spravovaného kódu můžete přidat krok po sestavení následujícím způsobem:  
  
```  
regasm /tlb MyAssembly.dll  
```  
  
## <a name="see-also"></a>Viz také  
 [Používání a poskytování služeb](../extensibility/using-and-providing-services.md)   
 [Základy služeb](../extensibility/internals/service-essentials.md)