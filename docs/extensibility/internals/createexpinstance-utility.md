---
title: Nástroj CreateExpInstance | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bdcb37374c63b96e2169de28c6fe21742024ca98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="createexpinstance-utility"></a>Nástroj CreateExpInstance
Použít nástroj CreateExpInstance k vytvoření, resetovat, nebo odstranit experimentální instanci sady Visual Studio. Experimentální instanci slouží k ladění a testování rozšíření Visual Studia beze změny základního produktu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### <a name="parameters"></a>Parametry  
 Nebo vytvořit  
 Vytvoří instanci experimentální.  
  
 / Reset  
 Odstraní experimentální instance a poté vytvoří nový.  
  
 /Clean  
 Odstraní experimentální instanci.  
  
 / VSInstance  
 Název adresáře, který obsahuje základní instanci sady Visual Studio pro kopírování.  
  
 / RootSuffix  
 Přípona pro připojení k názvu experimentální instanci adresáře.  
  
## <a name="remarks"></a>Poznámky  
 Když pracujete v rozšíření sady Visual Studio, můžete stisknutím klávesy F5 otevřete výchozí instance experimentální a nainstalovat aktuální rozšíření. Pokud je k dispozici není žádná instance experimentální, Visual Studio vytvoří jeden, který má výchozí nastavení.  
  
 Výchozí umístění experimentální instanci závisí na číslo verze sady Visual Studio. Například pro Visual Studio 2015, je umístění %localappdata%\Microsoft\VisualStudio\14.0Exp\ všechny soubory v umístění adresáře jsou považovány za součást této instance. Žádné další instance experimentální nebude načtena Visual Studio, pokud název adresáře se změní na výchozí umístění.  
  
 Visual Studio není přístup do registru systému, po jejím otevření experimentální instanci. To se liší od starších verzí sady Visual Studio, který používá experimentální verzi podregistru.  
  
 Nástroj CreateExpInstance nahrazuje nástroj VsRegEx.  
  
 Následující příklad Resetuje výchozí instance experimentální sady Visual Studio.  
  
 **/ Reset CreateExpInstance.exe /VSInstance = 14.0 /RootSuffix = Exp**  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)