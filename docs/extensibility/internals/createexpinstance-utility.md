---
title: Nástroj CreateExpInstance | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ed03833b6c109ca78feb86c1cfe41fa453022c66
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341919"
---
# <a name="createexpinstance-utility"></a>Nástroj CreateExpInstance
Použití **CreateExpInstance** nástroj k vytvoření, obnovit nebo odstranit experimentální instanci sady Visual Studio. Experimentální instanci slouží k ladění a testování rozšíření sady Visual Studio beze změny základní produkt.

## <a name="syntax"></a>Syntaxe

```
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix
```

## <a name="parameters"></a>Parametry
 **/ Vytvoření** vytvoří experimentální instanci aplikace.

 **/ Resetování** odstraní experimentální instanci a potom vytvoří nový.

 **/ Clean** odstraní experimentální instanci aplikace.

 **/ VSInstance** název adresáře, který obsahuje základní instance sady Visual Studio ke kopírování.

 **/ RootSuffix** přípona pro připojení k názvu adresáře experimentální instanci aplikace.

## <a name="remarks"></a>Poznámky
 Při práci na rozšíření sady Visual Studio, můžete stisknutím klávesy F5 spusťte výchozí experimentální instanci a nainstalujte aktuální rozšíření. Pokud je k dispozici žádná experimentální instance, vytvoří Visual Studio, pokud má výchozí nastavení.

 Výchozí umístění experimentální instanci aplikace závisí na číslo verze sady Visual Studio. Například pro sadu Visual Studio 2015 je umístění *%localappdata%\Microsoft\VisualStudio\14.0Exp\\* . Všechny soubory v umístění adresáře jsou považovány za součást této instance. Všechny další experimentální instance nebude načten pomocí sady Visual Studio, pokud název adresáře se změní na výchozí umístění.

 Visual Studio nepřistupuje k systémovým registrem při otevření experimentální instanci aplikace. Tím se liší od předchozí verze sady Visual Studio, který používá experimentální verzi podregistr registru.

 **CreateExpInstance** nahrazuje nástroj **VsRegEx** nástroj.

 Následující příklad Resetuje výchozí experimentální instanci sady Visual Studio:

 **CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp**

## <a name="see-also"></a>Viz také:
- [Balíčky VSPackage](../../extensibility/internals/vspackages.md)