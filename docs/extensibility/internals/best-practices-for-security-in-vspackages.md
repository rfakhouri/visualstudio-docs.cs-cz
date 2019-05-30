---
title: Osvědčené postupy pro zabezpečení v balíčcích VSPackage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 144bc62176ebc552e7070b29088acf70329a84d4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66309157"
---
# <a name="best-practices-for-security-in-vspackages"></a>Osvědčené postupy pro zabezpečení v balíčcích VSPackage
Chcete-li nainstalovat [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] na svém počítači musí běžet v kontextu s přihlašovacími údaji správce. Základní jednotka zabezpečení a nasazení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aplikace je [VSPackage](../../extensibility/internals/vspackages.md). VSPackage musí být registrovány pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], což také vyžaduje přihlašovací údaje pro správu.

 Správci mají úplná oprávnění k zápisu do registru a systém souborů a pro spuštění jakéhokoli kódu. Musíte mít tato oprávnění pro vývoj, Nenasazuje ani nainstaluje VSPackage.

 Jakmile je nainstalovaný, je plně důvěryhodné VSPackage. Z důvodu tento vysoký stupeň oprávnění přidružené k VSPackage je možné nainstalovat neúmyslně VSPackage, která se zlými úmysly.

 Uživatelé se ujistěte, že instalace rozšíření VSPackages pouze z důvěryhodných zdrojů. Společnosti vývoj rozšíření VSPackages by měla důrazně název a je podepište, aby bylo zaručeno, že manipulaci je zabráněno. Vývoj rozšíření VSPackages společnosti měli zkontrolovat jejich externí závislosti, jako jsou webové služby a vzdálenou instalaci, vyhodnocení a opravte všechny problémy se zabezpečením.

 Další informace najdete v tématu [zabezpečené kódování zásady pro rozhraní .NET Framework](/previous-versions/visualstudio/visual-studio-2008/d55zzx87(v=vs.90)).

## <a name="see-also"></a>Viz také:
- [Zabezpečení doplňku](https://msdn.microsoft.com/Library/44a5c651-6246-4310-b371-65378917c799)
- [DDEX zabezpečení](https://msdn.microsoft.com/library/44a52a70-5c98-450e-993d-4a3b32f69ba8)