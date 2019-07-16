---
title: Nástroj CreateExpInstance | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7d778f0f31a7651412915a898bff9e4bdfe6c55f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68196979"
---
# <a name="createexpinstance-utility"></a>Nástroj CreateExpInstance
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Použijte nástroj CreateExpInstance k vytvoření, obnovení, nebo odstranit experimentální instanci sady Visual Studio. Experimentální instanci slouží k ladění a testování rozšíření sady Visual Studio beze změny základní produkt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### <a name="parameters"></a>Parametry  
 / Vytvoření  
 Vytvoří experimentální instanci aplikace.  
  
 / Reset  
 Odstraní experimentální instanci a pak vytvoří nový.  
  
 /Clean  
 Odstraní experimentální instanci aplikace.  
  
 / VSInstance  
 Název adresáře, který obsahuje základní instance sady Visual Studio ke kopírování.  
  
 /RootSuffix  
 Přípona pro připojení k názvu adresáře experimentální instanci aplikace.  
  
## <a name="remarks"></a>Poznámky  
 Při práci na rozšíření sady Visual Studio, můžete stisknutím klávesy F5 spusťte výchozí experimentální instanci a nainstalujte aktuální rozšíření. Pokud je k dispozici žádná experimentální instance, vytvoří Visual Studio, pokud má výchozí nastavení.  
  
 Výchozí umístění experimentální instanci aplikace závisí na číslo verze sady Visual Studio. Například pro sadu Visual Studio 2015 je umístění %localappdata%\Microsoft\VisualStudio\14.0Exp\ všechny soubory v umístění adresáře jsou považovány za součást této instance. Všechny další experimentální instance nebude načten pomocí sady Visual Studio, pokud název adresáře se změní na výchozí umístění.  
  
 Visual Studio nepřistupuje k systémovým registrem při otevření experimentální instanci aplikace. Tím se liší od předchozí verze sady Visual Studio, který používá experimentální verzi podregistr registru.  
  
 Nástroj CreateExpInstance nahrazuje nástroj VsRegEx.  
  
 Následující příklad Resetuje výchozí experimentální instanci sady Visual Studio.  
  
 **CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp**  
  
## <a name="see-also"></a>Viz také  
 [Vydání produktu](../../misc/releasing-a-visual-studio-integration-product.md)
