---
title: Osvědčené postupy pro zabezpečení v VSPackages | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 689c85e090e44612a87474e8c77dc0e146706e84
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="best-practices-for-security-in-vspackages"></a>Doporučené postupy pro zabezpečení v VSPackages
K instalaci [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] v počítači, je třeba používat v souvislosti s přihlašovacími údaji správce. Základní jednotka zabezpečení a nasazení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aplikace je [VSPackages](../../extensibility/internals/vspackages.md). VSPackage musí být registrovaný pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], což také vyžaduje přihlašovací údaje pro správu.  
  
 Správci mají úplná oprávnění k zápisu do registru a systému souborů a nespouští žádný kód. Musí mít tato oprávnění pro vývoj, nasazení nebo nainstalujte VSPackage.  
  
 Jakmile je aplikace nainstalována, je VSPackage plně důvěryhodná. Z důvodu této vysokou úroveň oprávnění související s VSPackage je možné nainstalovat nechtěně VSPackage, který se zlými úmysly.  
  
 Uživatelé se ujistěte, že instalaci VSPackages pouze z důvěryhodných zdrojů. Společnosti vývoj VSPackages by měl silného názvu a jejich podpisu, zabránit, aby zajistil uživatele, že manipulaci. Vývoj VSPackages společností měli zkontrolovat jejich externí závislosti, jako jsou webové služby a vzdálenou instalaci, k vyhodnocení a opravte všechny problémy se zabezpečením.  
  
 Další informace najdete v tématu pokyny zabezpečení kódování pro rozhraní .NET Framework ([http://msdn.microsoft.com/library/d55zzx87.aspx](http://msdn.microsoft.com/library/d55zzx87.aspx)).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení doplňku](http://msdn.microsoft.com/Library/44a5c651-6246-4310-b371-65378917c799)   
 [DDEX zabezpečení](http://msdn.microsoft.com/en-us/44a52a70-5c98-450e-993d-4a3b32f69ba8)