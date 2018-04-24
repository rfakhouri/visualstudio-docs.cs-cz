---
title: '&lt;trustInfo&gt; – Element (aplikace ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 516ed9ae36b97a75e5185c69b89fadf587ddeaa7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="lttrustinfogt-element-clickonce-application"></a>&lt;trustInfo&gt; – Element (ClickOnce aplikace)
Popisuje minimální oprávnění požadovaná pro aplikaci spustit v klientském počítači.  
  
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
 `trustInfo` Element je povinná a je v `asm.v2` oboru názvů. Nemá žádné atributy a obsahuje následující prvky.  
  
## <a name="security"></a>zabezpečení  
 Požadováno. Tento element je podřízená `trustInfo` elementu. Obsahuje `applicationRequestMinimum` elementu a nemá žádné atributy.  
  
## <a name="applicationrequestminimum"></a>applicationRequestMinimum  
 Požadováno. Tento element je podřízená `security` elementu a obsahuje `PermissionSet`, `assemblyRequest`, a `defaultAssemblyRequest`elementy. Tento element nemá žádné atributy.  
  
## <a name="permissionset"></a>Assert  
 Požadováno. Tento element je podřízená `applicationRequestMinimum` elementu a obsahuje `IPermission` elementu. Tento element má následující atributy.  
  
-   `ID`  
  
     Požadováno. Identifikuje sadu oprávnění. Tento atribut může být libovolná hodnota. ID odkazuje `defaultAssemblyRequest` a `assemblyRequest` atributy.  
  
-   `version`  
  
     Požadováno. Identifikuje verzi oprávnění. Obvykle je tato hodnota `1`.  
  
## <a name="ipermission"></a>IPermission  
 Volitelné. Tento element je podřízená `PermissionSet` elementu. `IPermission` Element plně identifikuje třída oprávnění v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. `IPermission` Element má následující atributy, ale může mít další atributy, které odpovídají vlastnosti třídy oprávnění. Syntaxe pro konkrétní oprávnění naleznete v části Příklady uvedené v souboru Security.config.  
  
-   `class`  
  
     Požadováno. Označuje třídu oprávnění pomocí silného názvu. Například následující kód identifikuje `FileDialogPermission` typu.  
  
     `System.Security.Permissions.FileDialogPermission, mscorlib, Version=1.2.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
-   `version`  
  
     Požadováno. Identifikuje verzi oprávnění. Tato hodnota je obvykle `1`.  
  
-   `Unrestricted`  
  
     Požadováno. Určuje, jestli aplikace potřebuje neomezená tohoto oprávnění. Pokud `true`, udělení oprávnění nepodmíněné. Pokud `false`, nebo pokud tento atribut není definován, je omezen atributy specifické pro oprávnění definovaných na `IPermission` značky. Proveďte následující oprávnění:  
  
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
  
     V tomto příkladu deklarace pro <xref:System.Security.Permissions.EnvironmentPermission> omezí aplikaci pouze pro čtení v prostředí proměnné uživatelského jména, zatímco deklarace pro <xref:System.Security.Permissions.FileDialogPermission> poskytuje aplikaci neomezené využívání všechny <xref:System.Windows.Forms.FileDialog> třídy.  
  
## <a name="defaultassemblyrequest"></a>defaultAssemblyRequest  
 Volitelné. Identifikuje sadu oprávnění udělená sestavení. Tento element je podřízená `applicationRequestMinimum` elementu a má následující atribut.  
  
-   `permissionSetReference`  
  
     Požadováno. Určuje ID sady oprávnění, která je výchozí oprávnění. Nastavení oprávnění je deklarováno v `PermissionSet` elementu.  
  
## <a name="assemblyrequest"></a>assemblyRequest  
 Volitelné. Určuje oprávnění pro konkrétní sestavení. Tento element je podřízená `applicationRequestMinimum` elementu a má následující atributy.  
  
-   `Name`  
  
     Požadováno. Určuje název sestavení.  
  
-   `permissionSetReference`  
  
     Požadováno. Určuje ID sady oprávnění, která vyžaduje toto sestavení. Nastavení oprávnění je deklarováno v `PermissionSet` elementu.  
  
## <a name="requestedprivileges"></a>requestedPrivileges  
 Volitelné. Tento element je podřízená `security` elementu a obsahuje `requestedExecutionLevel` elementu. Tento element nemá žádné atributy.  
  
## <a name="requestedexecutionlevel"></a>requestedExecutionLevel  
 Volitelné. Určuje úroveň zabezpečení, ve kterém aplikace požádá o spuštění. Tento prvek nemá žádné podřízené objekty a má následující atributy.  
  
-   `Level`  
  
     Požadováno. Označuje, že úroveň zabezpečení aplikace požaduje. Možné hodnoty jsou:  
  
     `asInvoker`, požaduje žádná další oprávnění. Tato úroveň vyžaduje že vyzve žádný další vztah důvěryhodnosti.  
  
     `highestAvailable`, požadující nejvyšší oprávnění nadřazeného procesu k dispozici.  
  
     `requireAdministrator`, vyžaduje oprávnění správce s úplnými oprávněními.  
  
     [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace je možné instalovat pouze s hodnotou `asInvoker`. Instalace s jakoukoli jinou hodnotu, se nezdaří.  
  
-   `uiAccess`  
  
     Volitelné. Určuje, zda aplikace vyžaduje přístup k prvkům chráněného uživatelského rozhraní. Hodnoty jsou buď `true` nebo `false`, a výchozí hodnota je false. Pouze podepsané aplikace by měl mít hodnotu true.  
  
## <a name="remarks"></a>Poznámky  
 Pokud [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace požaduje další oprávnění, než klient poskytne ve výchozím nastavení jsou běžné jazyk správce vztahu důvěryhodnosti modulu runtime požádá uživatele, pokud chce poskytnout aplikace tuto zvýšenou úroveň důvěryhodnosti. Pokud se říká: Ne, aplikace se nespustí; jinak se spustí s požadovanými oprávněními.  
  
 Všechna oprávnění požadovaná pomocí `defaultAssemblyRequest` a `assemblyRequest` budou udělena bez vyzvání uživatele, pokud manifest nasazení má platnou licenci.  
  
 Další informace o zvýšení úrovně oprávnění najdete v tématu [zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md). Další informace o nasazení zásad najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
## <a name="examples"></a>Příklady  
 Následující příklady tři kódu ilustrují `trustInfo` prvky pro výchozí s názvem zóny zabezpečení – Internet, LocalIntranet a FullTrust – pro použití v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu nasazení aplikace.  
  
 V prvním příkladu ukazuje `trustInfo` element pro výchozí oprávnění, který je k dispozici v Internetové zóně zabezpečení.  
  
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
  
 Druhý příklad ukazuje `trustInfo` element pro výchozí oprávnění, který je k dispozici v zóně zabezpečení LocalIntranet.  
  
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
  
 Třetí příklad ukazuje `trustInfo` element pro výchozí oprávnění, který je k dispozici v zóně zabezpečení FullTrust.  
  
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