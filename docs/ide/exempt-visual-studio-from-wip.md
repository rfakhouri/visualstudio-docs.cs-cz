---
title: Vyloučení ze služby Windows Information Protection
ms.date: 06/01/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 665a4e893b8b146555dd35caad5cc521e1630dd9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891502"
---
# <a name="configure-visual-studio-as-a-wip-exempt-app"></a>Konfigurace sady Visual Studio jako aplikaci WIP – výjimka

[Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) (WIP) pomáhá chránit podniková data, abyste zabránili úniku prostřednictvím aplikace, jako jsou e-mailu, sociálních médií a veřejného cloudu, které jsou mimo firemní ovládacího prvku. WIP pomáhá chránit před úniky dat na zařízeních ve vlastnictví společnosti a osobních zařízeních bez vyžadování změny prostředí nebo jiných aplikací.

*Kompatibilních s* aplikace pro WIP se očekává podniková data zabránit v přechodu do nechráněné síťových umístění a vyhnout se šifrováním osobní údaje. Visual Studio není aplikaci s podporou WIP, takže nebude fungovat v prostředích s podporou WIP, pokud je to s výjimkou. Postupujte podle kroků v tomto článku, která sadě Visual Studio do funkce na počítač s podporou WIP.

## <a name="configure-vs-as-a-wip-exempt-app"></a>Konfigurace VS jako aplikace s výjimkou WIP

Můžete od WIP omezení s výjimkou sady Visual Studio, ale stále mohla používat podniková data. WIP výjimkou aplikací můžete připojit k podnikové cloudové prostředky pomocí IP adresy nebo názvu hostitele. Bez šifrování se použije a bude mít aplikace přístup místní soubory.

Pokud chcete určit výjimku pro aplikaci Visual Studio z WIP, postupujte [kroky pro desktopové aplikace s výjimkou](/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure#exempt-apps-from-a-wip-policy).

## <a name="create-a-wip-exempt-applocker-policy-file"></a>Vytvořte soubor zásad nástroje AppLocker WIP – výjimka

Vzhledem k tomu, že sada Visual Studio obsahuje více binárních souborů, [vytvořit soubor zásad nástroje AppLocker WIP výjimkou](/windows/security/threat-protection/windows-defender-application-control/applocker/run-the-automatically-generate-rules-wizard). AppLocker umožňuje automaticky generovat pravidla pro všechny soubory ve složce.

## <a name="add-appcompat-to-the-enterprise-cloud-resource-policy"></a>Přidat AppCompat podnikové zásady prostředků cloudu

Chcete-li určit, kde se Visual Studio můžete přistupovat k podnikovým datům ve vaší síti, postupujte podle těchto [kroky k definování, kde můžou chráněné aplikace najít a odeslat podniková data](/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure#choose-where-apps-can-access-enterprise-data). Pokud chcete zastavit Windows blokovat připojení ke cloudovým prostředkům prostřednictvím IP adresy, ujistěte se, že chcete přidat /\*AppCompat\*/ řetězec, který se nastavení.

## <a name="see-also"></a>Viz také:

- [Chování aplikace s WIP](/windows/security/information-protection/windows-information-protection/app-behavior-with-wip)