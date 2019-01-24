---
title: Osvědčené postupy pro zabezpečení v balíčcích VSPackage | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1db578f62e6fe42ba3d74df5870ca727bd884aaf
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54772185"
---
# <a name="best-practices-for-security-in-vspackages"></a>Osvědčené postupy pro zabezpečení v balíčcích VSPackage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Chcete-li nainstalovat [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] na svém počítači musí běžet v kontextu s přihlašovacími údaji správce. Základní jednotka zabezpečení a nasazení [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] aplikace je [rozšíření VSPackages](../../extensibility/internals/vspackages.md). VSPackage musí být registrovány pomocí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], což také vyžaduje přihlašovací údaje pro správu.  
  
 Správci mají úplná oprávnění k zápisu do registru a systém souborů a pro spuštění jakéhokoli kódu. Musíte mít tato oprávnění pro vývoj, Nenasazuje ani nainstaluje VSPackage.  
  
 Jakmile je nainstalovaný, je plně důvěryhodné VSPackage. Z důvodu tento vysoký stupeň oprávnění přidružené k VSPackage je možné nainstalovat neúmyslně VSPackage, která se zlými úmysly.  
  
 Uživatelé se ujistěte, že instalace rozšíření VSPackages pouze z důvěryhodných zdrojů. Společnosti vývoj rozšíření VSPackages by měla důrazně název a je podepište, aby bylo zaručeno, že manipulaci je zabráněno. Vývoj rozšíření VSPackages společnosti měli zkontrolovat jejich externí závislosti, jako jsou webové služby a vzdálenou instalaci, vyhodnocení a opravte všechny problémy se zabezpečením.  
  
 Další informace najdete v tématu zabezpečené kódování zásady pro rozhraní .NET Framework ([http://msdn.microsoft.com/library/d55zzx87.aspx](http://msdn.microsoft.com/library/d55zzx87.aspx)).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení doplňku](http://msdn.microsoft.com/library/44a5c651-6246-4310-b371-65378917c799)   
 [DDEX zabezpečení](http://msdn.microsoft.com/44a52a70-5c98-450e-993d-4a3b32f69ba8)
