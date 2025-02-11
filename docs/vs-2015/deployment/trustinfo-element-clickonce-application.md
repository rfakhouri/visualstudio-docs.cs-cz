---
title: '&lt;trustInfo&gt; – Element (aplikace ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#IPermission
- urn:schemas-microsoft-com:asm.v2#PermissionSet
- urn:schemas-microsoft-com:asm.v2#assemblyRequest
- urn:schemas-microsoft-com:asm.v2#trustInfo
- urn:schemas-microsoft-com:asm.v2#defaultAssemblyRequest
- urn:schemas-microsoft-com:asm.v2#security
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- manifests [ClickOnce], trustInfo element
- <trustInfo> element [ClickOnce application manifest]
ms.assetid: 8a813a74-e158-4308-be78-565937f6af83
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ca7e19925288b1509fec08235f546b84b4afffef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62420076"
---
# <a name="lttrustinfogt-element-clickonce-application"></a>&lt;trustInfo&gt; – Element (aplikace ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Popisuje minimální oprávnění požadovaná pro aplikaci, aby běžela v klientském počítači.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <trustInfo>  
   <security>  
      <applicationRequestMinimum>  
         <PermissionSet  
            ID  
            Unrestricted>  
            <IPermission  
               class  
               version  
               Unrestricted  
            />  
         </PermissionSet>  
         <defaultAssemblyRequest  
            permissionSetReference  
         />  
         <assemblyRequest  
            name  
            permissionSetReference  
         />  
      </applicationRequestMinimum>  
      <requestedPrivileges>  
         <requestedExecutionLevel  
            level  
            uiAccess  
         />  
      </requestedPrivileges>  
   </security>  
</trustInfo>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `trustInfo` Element je povinný a je v `asm.v2` oboru názvů. Nemá žádné atributy a obsahuje následující prvky.  
  
## <a name="security"></a>zabezpečení  
 Povinný parametr. Tento element je podřízeným prvkem `trustInfo` elementu. Obsahuje `applicationRequestMinimum` elementu a nemá žádné atributy.  
  
## <a name="applicationrequestminimum"></a>applicationRequestMinimum  
 Povinný parametr. Tento element je podřízeným prvkem `security` elementu a obsahuje `PermissionSet`, `assemblyRequest`, a `defaultAssemblyRequest`elementy. Tento element nemá žádné atributy.  
  
## <a name="permissionset"></a>PermissionSet  
 Povinný parametr. Tento element je podřízeným prvkem `applicationRequestMinimum` elementu a obsahuje `IPermission` elementu. Tento element má následující atributy.  
  
- `ID`  
  
     Povinný parametr. Určuje sadu oprávnění. Tento atribut může být libovolná hodnota. ID odkazuje `defaultAssemblyRequest` a `assemblyRequest` atributy.  
  
- `version`  
  
     Povinný parametr. Určuje verzi oprávnění. Obvykle je tato hodnota `1`.  
  
## <a name="ipermission"></a>Rozhraní IPermission.  
 Volitelné. Tento element je podřízeným prvkem `PermissionSet` elementu. `IPermission` Plně identifikuje třída oprávnění v elementu [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. `IPermission` Element má následující atributy, ale mohou mít další atributy, které odpovídají vlastnosti třídy oprávnění. Syntaxe pro konkrétní oprávnění najdete příklady uvedené v souboru Security.config.  
  
- `class`  
  
     Povinný parametr. Určuje třídu oprávnění pomocí silného názvu. Například následující kód označuje `FileDialogPermission` typu.  
  
     `System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
- `version`  
  
     Povinný parametr. Určuje verzi oprávnění. Tato hodnota je obvykle `1`.  
  
- `Unrestricted`  
  
     Povinný parametr. Označuje, zda aplikace potřebuje neomezená oprávnění. Pokud `true`, udělení oprávnění Nepodmíněný. Pokud `false`, nebo pokud tento atribut není definován, je omezen atributy specifické pro oprávnění definované na `IPermission` značky. Proveďte následující oprávnění:  
  
    ```  
    <IPermission  
      class="System.Security.Permissions.EnvironmentPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
      version="1"   
      Read="USERNAME" />  
    <IPermission  
      class="System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
      version="1"   
      Unrestricted="true" />  
    ```  
  
     V tomto příkladu deklarace <xref:System.Security.Permissions.EnvironmentPermission> omezí aplikace pro čtení jenom proměnné prostředí uživatelské jméno, zatímco deklarace <xref:System.Security.Permissions.FileDialogPermission> poskytuje aplikaci neomezené použití operátoru all <xref:System.Windows.Forms.FileDialog> třídy.  
  
## <a name="defaultassemblyrequest"></a>defaultAssemblyRequest  
 Volitelné. Identifikuje sadu oprávnění udělená všechna sestavení. Tento element je podřízeným prvkem `applicationRequestMinimum` elementu a nemá tento atribut.  
  
- `permissionSetReference`  
  
     Povinný parametr. Určuje ID sady oprávnění, která je výchozí oprávnění. Sada oprávnění je deklarován v `PermissionSet` elementu.  
  
## <a name="assemblyrequest"></a>assemblyRequest  
 Volitelné. Určuje oprávnění pro konkrétní sestavení. Tento element je podřízeným prvkem `applicationRequestMinimum` prvek a má následující atributy.  
  
- `Name`  
  
     Povinný parametr. Určuje název sestavení.  
  
- `permissionSetReference`  
  
     Povinný parametr. Určuje ID sady oprávnění, která toto sestavení vyžaduje. Sada oprávnění je deklarován v `PermissionSet` elementu.  
  
## <a name="requestedprivileges"></a>requestedPrivileges  
 Volitelné. Tento element je podřízeným prvkem `security` elementu a obsahuje `requestedExecutionLevel` elementu. Tento element nemá žádné atributy.  
  
## <a name="requestedexecutionlevel"></a>requestedExecutionLevel  
 Volitelné. Určuje úroveň zabezpečení, ve kterém aplikace požádá o který se spustí. Tento element nemá žádné podřízené položky a má následující atributy.  
  
- `Level`  
  
     Povinný parametr. Označuje, že úroveň zabezpečení aplikace požaduje. Možné hodnoty jsou:  
  
     `asInvoker`, požadování žádná další oprávnění. Tato úroveň vyžaduje že důvěryhodnosti žádné další výzvy.  
  
     `highestAvailable`, požadování nejvyšší oprávnění, která je k dispozici nadřazenému procesu.  
  
     `requireAdministrator`, vyžaduje oprávnění správce s úplnými oprávněními.  
  
     [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace bude instalovat pouze s hodnotou `asInvoker`. Instalace s jakoukoli jinou hodnotu se nezdaří.  
  
- `uiAccess`  
  
     Volitelné. Určuje, jestli aplikace vyžaduje přístup k prvkům chráněného uživatelského rozhraní. Hodnoty jsou buď `true` nebo `false`, a výchozí hodnota je false. Pouze podepsané aplikace by měla mít hodnotu true.  
  
## <a name="remarks"></a>Poznámky  
 Pokud [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace požaduje více oprávnění než klientský počítač, udělí se ve výchozím nastavení, CLR správce důvěryhodnosti modulu CLR runtime požádá uživatele, pokud chce poskytnout aplikace tuto zvýšenou úroveň důvěryhodnosti. Pokud uživatel je hodnota Ne, aplikace se nespustí; v opačném případě bude spuštěna s požadovaná oprávnění.  
  
 Všechna oprávnění požadovaná pomocí `defaultAssemblyRequest` a `assemblyRequest` udělí bez vyzvání uživatele, pokud manifest nasazení nemá platnou licenci.  
  
 Další informace o zvýšení úrovně oprávnění najdete v tématu [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md). Další informace o nasazení zásad najdete v tématu [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md).  
  
## <a name="examples"></a>Příklady  
 Následující tři příklady ilustrují `trustInfo` elementy pro výchozí hodnotu s názvem zóny zabezpečení – Internet, LocalIntranet a FullTrust – pro použití v [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] manifest aplikace tohoto nasazení.  
  
 První příklad ukazuje, `trustInfo` – element pro výchozí oprávnění, který je k dispozici v zóně zabezpečení Internetu.  
  
```  
<trustInfo>  
    <security>  
      <applicationRequestMinimum>  
        <PermissionSet ID="Internet">  
          <IPermission  
            class="System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Access="Open" />  
          <IPermission  
           class="System.Security.Permissions.IsolatedStorageFilePermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"  
            Allowed="DomainIsolationByUser"  
            UserQuota="10240" />  
          <IPermission  
            class="System.Security.Permissions.SecurityPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Flags="Execution" />  
          <IPermission   
            class="System.Security.Permissions.UIPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Window="SafeTopLevelWindows"  
            Clipboard="OwnClipboard" />  
          <IPermission  
            class="System.Drawing.Printing.PrintingPermission, System.Drawing, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
            version="1"   
            Level="SafePrinting" />  
        </PermissionSet>  
        <defaultAssemblyRequest permissionSetReference="Internet" />  
      </applicationRequestMinimum>  
    </security>  
  </trustInfo>  
```  
  
 Druhý příklad ukazuje, `trustInfo` – element pro výchozí oprávnění, který je k dispozici v zóně zabezpečení LocalIntranet.  
  
```  
<trustInfo>  
    <security>  
      <applicationRequestMinimum>  
        <PermissionSet ID="LocalIntranet">  
          <IPermission  
            class="System.Security.Permissions.EnvironmentPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Read="USERNAME" />  
          <IPermission  
            class="System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Unrestricted="true" />  
          <IPermission  
            class="System.Security.Permissions.IsolatedStorageFilePermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Allowed="AssemblyIsolationByUser"  
            UserQuota="9223372036854775807"  
            Expiry="9223372036854775807"  
            Permanent="True" />  
          <IPermission  
            class="System.Security.Permissions.ReflectionPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Flags="ReflectionEmit" />  
          <IPermission  
            class="System.Security.Permissions.SecurityPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"   
            version="1"   
            Flags="Assertion, Execution" />  
          <IPermission   
            class="System.Security.Permissions.UIPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Unrestricted="true" />  
          <IPermission  
            class="System.Net.DnsPermission, System, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1"   
            Unrestricted="true" />  
          <IPermission  
            class="System.Drawing.Printing.PrintingPermission, System.Drawing, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
            version="1"  
            Level="DefaultPrinting" />  
          <IPermission  
            class="System.Diagnostics.EventLogPermission, System, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
            version="1" />  
        </PermissionSet>  
        <defaultAssemblyRequest permissionSetReference="LocalIntranet" />  
      </applicationRequestMinimum>  
    </security>  
</trustInfo>  
```  
  
 Třetí příklad ukazuje, `trustInfo` – element pro výchozí oprávnění, který je k dispozici v zóně zabezpečení FullTrust.  
  
```  
<trustInfo>  
  <security>  
    <applicationRequestMinimum>  
      <PermissionSet ID="FullTrust" Unrestricted="true" />  
      <defaultAssemblyRequest permissionSetReference="FullTrust" />  
    </applicationRequestMinimum>  
  </security>  
</trustInfo>  
```  
  
## <a name="see-also"></a>Viz také  
 [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md)   
 [ClickOnce – manifest aplikace ](../deployment/clickonce-application-manifest.md)
