---
title: "&lt;Příkazy&gt; prvek (zavaděče) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords: <Commands> element [bootstrapper]
ms.assetid: e61d5787-fe1f-4ebf-b0cf-0d7909be7ffb
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: ac8580a1b930d4ad18db9eebb275e4eb67d80c62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="ltcommandsgt-element-bootstrapper"></a>&lt;Příkazy&gt; – Element (zaváděcího nástroje)
`Commands` Element implementuje testy popsané prvky pod `InstallChecks` elementu a deklaruje balíčky, které [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zaváděcího nástroje měli nainstalovat, pokud se test nezdaří.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Commands  
    Reboot  
>  
    <Command  
        PackageFile  
        Arguments  
        EstimatedInstallSeconds  
        EstimatedDiskBytes  
        EstimatedTempBytes  
        Log  
    >  
        <InstallConditions>  
            <BypassIf   
                Property  
                Compare  
                Value  
                Schedule  
            />  
            <FailIf   
                Property  
                Compare  
                Value  
                String  
                Schedule  
            />  
        </InstallConditions>  
        <ExitCodes>  
            <ExitCode   
                Value  
                Result  
                String  
            />  
        </ExitCodes>  
    </Command>  
</Commands>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `Commands` Prvek je nutný. Element obsahuje následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Reboot`|Volitelné. Určuje, zda by měl restart systému, pokud žádný z balíčků vrátí ukončovací kód restartování. V následujícím seznamu jsou platné hodnoty:<br /><br /> `Defer`. Restartování je odloženo až do příště.<br /><br /> `Immediate`. Způsobí okamžité restartování, pokud jeden z balíčků vrátil ukončovací kód restartování.<br /><br /> `None`. Způsobí, že všechny žádosti restart, budou ignorovány.<br /><br /> Výchozí hodnota je `Immediate`.|  
  
## <a name="command"></a>Příkaz  
 `Command` Element je podřízený element `Commands` elementu. A `Commands` element může obsahovat jednu nebo více `Command` elementy. Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`PackageFile`|Požadováno. Název balíčku pro instalaci má jeden nebo více podmínek určeného `InstallConditions` vrátí hodnotu false. Balíček musí být definován ve stejném souboru pomocí `PackageFile` elementu.|  
|`Arguments`|Volitelné. Sada argumenty příkazového řádku k předání do souboru balíčku.|  
|`EstimatedInstallSeconds`|Volitelné. Odhadovaný čas v sekundách, bude třeba k instalaci balíčku. Tato hodnota určuje velikost indikátoru průběhu, který zavaděč zobrazí uživateli. Výchozí hodnota je 0, v takovém případě žádný čas, který je zadán odhad.|  
|`EstimatedDiskBytes`|Volitelné. Odhadovaná velikost místa na disku v bajtech, které bude balíček zabírat po dokončení instalace je dokončena. Tato hodnota se používá v požadavky na místo pevného disku, které zavaděč zobrazí uživateli. Výchozí hodnota je 0, ve kterém zaváděcí nejsou zobrazeny žádné požadavky na místo na pevném disku.|  
|`EstimatedTempBytes`|Volitelné. Odhadovaná velikost dočasného prostoru na disku v bajtech, které bude vyžadovat balíček.|  
|`Log`|Volitelné. Cesta k souboru protokolu, který generuje balíček relativně k kořenový adresář balíčku.|  
  
## <a name="installconditions"></a>InstallConditions  
 `InstallConditions` Element je podřízená `Command` elementu. Každý `Command` element může obsahovat maximálně jeden `InstallConditions` elementu. Pokud žádné `InstallConditions` element existuje, balíček určený pomocí `Condition` bude vždy spuštěn.  
  
## <a name="bypassif"></a>BypassIf  
 `BypassIf` Element je podřízená `InstallConditions` elementu a popisuje pozitivní podmínky, pod kterým by neměl být příkaz provést. Každý `InstallConditions` element může obsahovat nula nebo více `BypassIf` elementy.  
  
 `BypassIf`má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti pro testování. Vlastnost musí být dříve definována podřízený `InstallChecks` elementu. Další informace najdete v tématu [ \<InstallChecks > Element](../deployment/installchecks-element-bootstrapper.md).|  
|`Compare`|Požadováno. Typ porovnání k provedení. V následujícím seznamu jsou platné hodnoty:<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|Požadováno. Hodnoty k porovnání s vlastností.|  
|`Schedule`|Volitelné. Název `Schedule` značku, která definuje, kdy by mělo být vyhodnoceno toto pravidlo.|  
  
## <a name="failif"></a>FailIf  
 `FailIf` Element je podřízená `InstallConditions` elementu a popisuje pozitivní podmínky, pod kterým bude instalace zastavena. Každý `InstallConditions` element může obsahovat nula nebo více `FailIf` elementy.  
  
 `FailIf`má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti pro testování. Vlastnost musí být dříve definována podřízený `InstallChecks` elementu. Další informace najdete v tématu [ \<InstallChecks > Element](../deployment/installchecks-element-bootstrapper.md).|  
|`Compare`|Požadováno. Typ porovnání k provedení. V následujícím seznamu jsou platné hodnoty:<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|Požadováno. Hodnoty k porovnání s vlastností.|  
|`String`|Volitelné. Text, který se má zobrazit uživateli při selhání.|  
|`Schedule`|Volitelné. Název `Schedule` značku, která definuje, kdy by mělo být vyhodnoceno toto pravidlo.|  
  
## <a name="exitcodes"></a>ExitCodes  
 `ExitCodes` Element je podřízená `Command` elementu. `ExitCodes` Element obsahuje jeden nebo více `ExitCode` elementy, které určují, co dělat v reakci na ukončovací kód z balíčku instalace. Může být jedna volitelné `ExitCode` element pod `Command` elementu. `ExitCodes`nemá žádné atributy.  
  
## <a name="exitcode"></a>exitCode  
 `ExitCode` Element je podřízená `ExitCodes` elementu. `ExitCode` Element určuje, co by měla provést instalaci v reakci na ukončovací kód z balíčku. `ExitCode`neobsahuje žádné podřízené prvky a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Value`|Požadováno. Hodnotu ukončovacího kódu, ke kterému tato `ExitCode` element platí.|  
|`Result`|Požadováno. Instalace měla jak reagovat na tento ukončovací kód. V následujícím seznamu jsou platné hodnoty:<br /><br /> `Success`. Označuje jako úspěšně nainstaloval balíček.<br /><br /> `SuccessReboot`. Označuje balíček jako úspěšně nainstalován a dává pokyn restartování systému.<br /><br /> `Fail`. Balíček se označuje jako neúspěšný.<br /><br /> `FailReboot`. Označuje balíček jako neúspěšný a dává pokyn restartování systému.|  
|`String`|Volitelné. Hodnota pro zobrazení pro uživatele v odpovědi na tento ukončovací kód.|  
|`FormatMessageFromSystem`|Volitelné. Určuje, jestli se má použít poskytované systémem chybová zpráva odpovídající ukončovací kód, nebo použijte hodnotu podle `String`. Platné hodnoty jsou `true`, což znamená použití poskytované systémem chyby, a `false`, což znamená použití řetězce poskytované `String`. Výchozí hodnota je `false`. Pokud je tato vlastnost `false`, ale `String` není nastaven, použije se chyba poskytované systémem.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu definuje příkazy pro instalaci rozhraní .NET Framework 2.0.  
  
```  
<Commands Reboot="Immediate">  
    <Command PackageFile="instmsia.exe"  
             Arguments= ' /q /c:"msiinst /delayrebootq"'  
             EstimatedInstallSeconds="20" >  
        <InstallConditions>  
           <BypassIf Property="VersionNT" Compare="ValueExists"/>  
             BypassIf Property="VersionMsi" Compare="VersionGreaterThanOrEqualTo" Value="2.0"/>  
        </InstallConditions>  
        <ExitCodes>  
            <ExitCode Value="0" Result="SuccessReboot"/>  
            <ExitCode Value="1641" Result="SuccessReboot"/>  
            <ExitCode Value="3010" Result="SuccessReboot"/>  
            <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
        </ExitCodes>  
    </Command>  
    <Command PackageFile="WindowsInstaller-KB884016-v2-x86.exe"  
             Arguments= '/quiet /norestart'   
             EstimatedInstallSeconds="20" >  
      <InstallConditions>  
          <BypassIf Property="Version9x" Compare="ValueExists"/>  
          <BypassIf Property="VersionNT" Compare="VersionLessThan" Value="5.0.3"/>  
          <BypassIf Property="VersionMsi" Compare="VersionGreaterThanOrEqualTo" Value="3.0"/>  
          <FailIf Property="AdminUser" Compare="ValueEqualTo" Value="false" String="AdminRequired"/>  
      </InstallConditions>  
      <ExitCodes>  
          <ExitCode Value="0" Result="Success"/>  
          <ExitCode Value="1641" Result="SuccessReboot"/>  
          <ExitCode Value="3010" Result="SuccessReboot"/>  
          <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
      </ExitCodes>  
    </Command>  
    <Command PackageFile="dotnetfx.exe"   
         Arguments=' /q:a /c:"install /q /l"'   
         EstimatedInstalledBytes="21000000"   
         EstimatedInstallSeconds="300">  
  
        <!-- These checks determine whether the package is to be installed -->  
        <InstallConditions>  
            <!-- Either of these properties indicates the .NET Framework is already installed -->  
            <BypassIf Property="DotNetInstalled" Compare="ValueNotEqualTo" Value="0"/>  
  
            <!-- Block install if user does not have adminpermissions -->  
            <FailIf Property="AdminUser" Compare="ValueEqualTo" Value="false" String="AdminRequired"/>  
  
            <!-- Block install on Windows 95 -->  
            <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatformWin9x"/>  
  
            <!-- Block install on Windows 2000 SP 2 or less -->  
            <FailIf Property="VersionNT" Compare="VersionLessThan" Value="5.0.3" String="InvalidPlatformWinNT"/>  
  
            <!-- Block install if Internet Explorer 5.01 or later is not present -->  
            <FailIf Property="IEVersion" Compare="ValueNotExists" String="InvalidPlatformIE" />  
            <FailIf Property="IEVersion" Compare="VersionLessThan" Value="5.01" String="InvalidPlatformIE" />  
  
            <!-- Block install if the operating system does not support x86 -->  
            <FailIf Property="ProcessorArchitecture" Compare="ValueNotEqualTo" Value="Intel" String="InvalidPlatformArchitecture" />  
       </InstallConditions>  
  
        <ExitCodes>  
            <ExitCode Value="0" Result="Success"/>  
            <ExitCode Value="3010" Result="SuccessReboot"/>  
            <ExitCode Value="4097" Result="Fail" String="AdminRequired"/>  
            <ExitCode Value="4098" Result="Fail" String="WindowsInstallerComponentFailure"/>  
            <ExitCode Value="4099" Result="Fail" String="WindowsInstallerImproperInstall"/>  
            <ExitCode Value="4101" Result="Fail" String="AnotherInstanceRunning"/>  
            <ExitCode Value="4102" Result="Fail" String="OpenDatabaseFailure"/>  
            <ExitCode Value="4113" Result="Fail" String="BetaNDPFailure"/>  
            <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
        </ExitCodes>  
  
    </Command>  
</Commands>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)   
 [\<InstallChecks > elementu](../deployment/installchecks-element-bootstrapper.md)