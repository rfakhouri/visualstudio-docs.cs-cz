---
title: Generateapplicationmanifest – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateApplicationManifest
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateApplicationManifest task
- HostInBrowser property (MSBuild)
- GenerateApplicationManifest task [MSBuild]
ms.assetid: a494102b-0cb2-4755-8e2a-d2c0f39fac1d
caps.latest.revision: 24
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 76a2fc5e184b566e0c9783f6f64beecc7ca882a2
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="generateapplicationmanifest-task"></a>GenerateApplicationManifest – úloha
Generuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace nebo nativní manifestu. Nativní manifestu popisuje součást definováním jedinečnou identitu pro součást a určíte všechny sestavení a soubory, které tvoří součásti. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace rozšiřuje nativní manifestu definovaných vstupní bod aplikace a zadání úroveň zabezpečení aplikace.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `GenerateApplicationManifest` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AssemblyName`|Volitelné `String` parametr.<br /><br /> Určuje, `Name` pole identity sestavení pro vygenerovaný manifest. Pokud není tento parametr zadán, je název odvodit z `EntryPoint` nebo `InputManifest` parametry. Pokud žádný název mohou být vytvořeny, úloha vrátí chybu.|  
|`AssemblyVersion`|Volitelné `String` parametr.<br /><br /> Určuje, `Version` pole identity sestavení pro vygenerovaný manifest. Pokud není tento parametr zadán, se používá výchozí hodnota je "1.0.0.0".|  
|`ClrVersion`|Volitelné `String` parametr.<br /><br /> Určuje minimální verzi nástroje CLR Common Language Runtime () požadované aplikací. Výchozí hodnota je verze CLR používá systém sestavení. Úloha vytváří nativní manifestu,-li tento parametr je ignorován.|  
|`ConfigFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje, která položka obsahuje konfigurační soubor aplikace. Úloha vytváří nativní manifestu,-li tento parametr je ignorován.|  
|`Dependencies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje seznam položek, který definuje sadu závislé sestavení pro vygenerovaný manifest. Každá položka může být dále označena metadata položky k označení stavu další nasazení a typ závislost. Další informace najdete v části "Metadata položky" níže.|  
|`Description`|Volitelné `String` parametr.<br /><br /> Určuje popis aplikací nebo součástí.|  
|`EntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje jednu položku, která určuje vstupní bod pro vygenerovaný manifest sestavení.<br /><br /> Pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace, tento parametr určuje sestavení, který se spustí při spuštění aplikace.|  
|`ErrorReportUrl`|Volitelné <xref:System.String?displayProperty=fullName> parametr.<br /><br /> Určuje adresu URL webové stránky, která se zobrazí v dialogových oknech při chybách v instalacích ClickOnce.|  
|`FileAssociations`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje seznam jeden nebo více typ souboru, které jsou přidruženy ClickOnce – manifest nasazení.<br /><br /> Přidružení souboru pouze platný, jenom když se rozhraní .NET Framework 3.5 nebo novější.|  
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Soubory, které mají být zahrnuty do manifestu. Zadejte úplnou cestu pro každý soubor.|  
|`HostInBrowser`|Volitelné <xref:System.Boolean> parametr.<br /><br /> Pokud `true`, aplikace je hostovaná v prohlížeči (jako jsou aplikace WPF webového prohlížeče).|  
|`IconFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje soubor ikony aplikace. Ikona aplikace je vyjádřeno v manifestu generovaného aplikace a slouží pro dialogové okno nabídce Start a přidat nebo odebrat programy. Pokud tento vstup není zadán, použije se výchozí ikona. Úloha vytváří nativní manifestu,-li tento parametr je ignorován.|  
|`InputManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje vstupní dokument XML sloužit jako základ pro generátor manifestu. To umožňuje strukturovaných dat, například zabezpečení aplikací nebo vlastní manifestu definice projeví v manifestu výstup. Kořenový element v dokumentu XML musí být do uzlu sestavení v oboru názvů asmv1.|  
|`IsolatedComReferences`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje komponenty COM a izolovat v vygenerovaný manifest. Tento parametr podporuje možnost izolovat COM – součásti pro nasazení "Registrace bezplatné COM". Funguje díky automatické generování manifestu s standardní definice registrace COM. Komponenty modelu COM, ale musí být registrovaný na počítači sestavení toto fungovat správně.|  
|`ManifestType`|Volitelné `String` parametr.<br /><br /> Určuje typ ke generování manifestu. Tento parametr může mít následující hodnoty:<br /><br /> -   `Native`<br />-   `ClickOnce`<br /><br /> Pokud není tento parametr zadán, úloha výchozí `ClickOnce`.|  
|`MaxTargetPath`|Volitelné `String` parametr.<br /><br /> Určuje maximální povolenou délku cesty k souboru v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace. Pokud je tato hodnota zadána, je tento limit kontrolovat délka cesty každý soubor v aplikaci. Všechny položky, které překračují limit vyvolá v sestavení upozornění. Pokud tento vstup není zadána nebo rovná nule, je provedena žádná kontrola. Úloha vytváří nativní manifestu,-li tento parametr je ignorován.|  
|`OSVersion`|Volitelné `String` parametr.<br /><br /> Určuje minimální požadovaný operační systém (OS) verzi požadované aplikací. Například hodnota "5.1.2600.0" označuje, že operační systém je Windows XP. Pokud není tento parametr zadán, je použita hodnota "4.10.0.0", což naznačuje Windows 98 Druhé vydání, minimální podporované OS rozhraní .NET Framework. Pokud úloha je generování manifestu nativní, tento vstup je ignorována.|  
|`OutputManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje název souboru manifestu generovaný výstup. Pokud není tento parametr zadán, je název souboru výstupního souboru odvodit z identity vygenerovaný manifest.|  
|`Platform`|Volitelné `String` parametr.<br /><br /> Určuje cílovou platformu aplikace. Tento parametr může mít následující hodnoty:<br /><br /> -   `AnyCPU`<br />-   `x86`<br />-   `x64`<br />-   `Itanium`<br /><br /> Pokud není tento parametr zadán, úloha výchozí `AnyCPU`.|  
|`Product`|Volitelné `String` parametr.<br /><br /> Určuje název aplikace. Pokud není tento parametr zadán, je název odvodit z identity vygenerovaný manifest. Tento název se používá pro název místní nabídky Start a je součástí názvu, který se zobrazí v dialogovém okně Přidat nebo odebrat programy.|  
|`Publisher`|Volitelné `String` parametr.<br /><br /> Určuje vydavatele aplikace. Pokud není tento parametr zadán, je název odvodit z registrovaní uživatelé, nebo identitu vygenerovaný manifest. Tento název se používá pro název složky v nabídce Start a je součástí názvu, který se zobrazí v dialogovém okně Přidat nebo odebrat programy.|  
|`RequiresMinimumFramework35SP1`|Volitelné `Boolean` parametr.<br /><br /> V případě hodnoty true aplikace vyžaduje rozhraní .NET Framework 3.5 SP1 nebo novější verzi.|  
|`TargetCulture`|Volitelné `String` parametr.<br /><br /> Jazyková verze aplikace identifikuje a určí `Language` pole identity sestavení pro vygenerovaný manifest. Pokud není tento parametr zadán, předpokládá se, že aplikace je neutrální jazykovou verzi.|  
|`TargetFrameworkMoniker`|Volitelné `String` parametr.<br /><br /> Určuje cílový framework přezdívka.|  
|`TargetFrameworkProfile`|Volitelné `String` parametr.<br /><br /> Určuje cílový framework profil.|  
|`TargetFrameworkSubset`|Volitelné `String` parametr.<br /><br /> Určuje název podmnožinu rozhraní .NET Framework k cíli.|  
|`TargetFrameworkVersion`|Volitelné `String` parametr.<br /><br /> Určuje cílový rozhraní .NET Framework projektu.|  
|`TrustInfoFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje dokument XML, který určuje zabezpečení aplikace. Kořenový element v dokumentu XML, musí být uzel trustInfo v oboru názvů asmv2. Úloha vytváří nativní manifestu,-li tento parametr je ignorován.|  
|`UseApplicationTrust`|Volitelné `Boolean` parametr.<br /><br /> V případě hodnoty true `Product`, `Publisher`, a `SupportUrl` vlastnosti se zapisují do manifestu aplikace.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.GenerateManifestBase> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam parametrů třída úlohy najdete v tématu [Třída Base úlohy](../msbuild/task-base-class.md).  
  
 Informace o tom, jak používat `GenerateDeploymentManifest` úloh najdete v tématu [generateapplicationmanifest – úloha](../msbuild/generateapplicationmanifest-task.md).  
  
 Vstupy pro závislosti a soubory může být dál doplněny pomocí metadata položky k určení stavu další nasazení pro každou položku.  
  
## <a name="item-metadata"></a>Metadata položky  
  
|Název metadat|Popis|  
|-------------------|-----------------|  
|`DependencyType`|Určuje, jestli závislost je publikována a nainstalovaný s předpokladem nebo aplikace. Tato metadata jsou platné pro všechny závislosti, ale nepoužívá pro soubory. Dostupné hodnoty pro tato metadata jsou:<br /><br /> -   `Install`<br />-   `Prerequisite`<br /><br /> Instalace je výchozí hodnota.|  
|`AssemblyType`|Určuje, jestli závislost je spravované nebo nativní sestavení. Tato metadata jsou platné pro všechny závislosti, ale nepoužívá pro soubory. Dostupné hodnoty pro tato metadata jsou:<br /><br /> -   `Managed`<br />-   `Native`<br />-   `Unspecified`<br /><br /> `Unspecified` je výchozí hodnotu, která určuje, zda generátor manifestu automaticky určí typ sestavení.|  
|`Group`|Označuje skupinu pro stahování další soubory na vyžádání. Název skupiny je definován aplikací a může být libovolný řetězec. Prázdný řetězec znamená, že soubor není součástí skupiny stahování, což je výchozí hodnota. Soubory nejsou ve skupině jsou součástí stažení počáteční aplikace. Soubory ve skupině jsou staženy pouze v případě explicitně požadavku aplikace pomocí <xref:System.Deployment.Application>.<br /><br /> Tato metadata jsou platné pro všechny soubory kde `IsDataFile` je `false` a všechny závislosti kde `DependencyType` je `Install`.|  
|`TargetPath`|Určuje, jak je nutné definovat cestu v vygenerovaný manifest. Tento atribut je platný pro všechny soubory. Pokud tento atribut nezadá, použije se specifikace položky. Tento atribut je platný pro všechny soubory a závislosti s `DependencyType` hodnotu `Install`.|  
|`IsDataFile`|A `Boolean` metadata hodnotu, která určuje, zda je soubor datový soubor. Datový soubor je speciální v tom, že nedojde k migraci mezi aktualizacemi aplikací. Tato metadata jsou platná pouze pro soubory. `False` je výchozí hodnota.|  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `GenerateApplicationManifest` úloh k vygenerování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace a `GenerateDeploymentManifest` úkolů ke generování manifestu nasazení pro aplikace pomocí jednoho sestavení. Poté použije `SignFile` úloh pro podepsání manifestů.  
  
 To ukazuje nejjednodušší scénář možné generování manifestu kde [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty jsou generovány pro jeden program. Výchozí název a identity jsou odvozené ze sestavení pro manifest.  
  
> [!NOTE]
>  V následujícím příkladu jsou předem připravené, aby bylo možné zaměřit na aspekty generování manifestu všechny binární soubory aplikace. Tento příklad vytvoří plně práce [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.  
  
> [!NOTE]
>  Další informace o `Thumbprint` vlastnost použitá v `SignFile` úloh v tomto příkladu najdete v tématu [signfile – úloha](../msbuild/signfile-task.md).  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            EntryPoint="@(EntryPoint)">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
            EntryPoint="@(ApplicationManifest)">  
            <Output  
                ItemName="DeployManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `GenerateApplicationManifest` a `GenerateDeploymentManifest` úlohy ke generování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace a nasazení manifesty pro aplikace pomocí jednoho sestavení, zadáte název a identity manifesty.  
  
 V tomto příkladu je podobná předchozí příklad, s výjimkou explicitně zadat název a identity manifestů. V tomto příkladu je navíc nakonfigurovaný jako online aplikace namísto aplikace nainstalované.  
  
> [!NOTE]
>  V následujícím příkladu jsou předem připravené, aby bylo možné zaměřit na aspekty generování manifestu všechny binární soubory aplikace. Tento příklad vytvoří plně práce [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.  
  
> [!NOTE]
>  Další informace o `Thumbprint` vlastnost použitá v `SignFile` úloh v tomto příkladu najdete v tématu [signfile – úloha](../msbuild/signfile-task.md).  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            AssemblyName="SimpleWinApp.exe"  
            AssemblyVersion="1.0.0.0"  
            EntryPoint="@(EntryPoint)"  
            OutputManifest="SimpleWinApp.exe.manifest">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
                AssemblyName="SimpleWinApp.application"  
                AssemblyVersion="1.0.0.0"  
                EntryPoint="@(ApplicationManifest)"  
                Install="false"  
                OutputManifest="SimpleWinApp.application">  
                <Output  
                    ItemName="DeployManifest"  
                    TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `GenerateApplicationManifest` a `GenerateDeploymentManifest` úlohy ke generování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace a nasazení manifesty pro aplikace s více soubory a sestavení.  
  
> [!NOTE]
>  V následujícím příkladu jsou předem připravené, aby bylo možné zaměřit na aspekty generování manifestu všechny binární soubory aplikace. Tento příklad vytvoří plně práce [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.  
  
> [!NOTE]
>  Další informace o `Thumbprint` vlastnost použitá v `SignFile` úloh v tomto příkladu najdete v tématu [signfile – úloha](../msbuild/signfile-task.md).  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
        <DeployUrl>  
            <!-- Insert the deployment URL here -->  
        </DeployUrl>  
        <SupportUrl>  
            <!-- Insert the support URL here -->  
        </SupportUrl>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe"/>  
        <Dependency Include="ClassLibrary1.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
        </Dependency>  
        <Dependency Include="ClassLibrary2.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
            <Group>Secondary</Group>  
        </Dependency>  
        <Dependency Include="MyAddIn1.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
            <TargetPath>Addins\MyAddIn1.dll</TargetPath>  
        </Dependency>  
        <Dependency Include="ClassLibrary3.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Prerequisite</DependencyType>  
        </Dependency>  
  
        <File Include="Text1.txt">  
            <TargetPath>Text\Text1.txt</TargetPath>  
            <Group>Text</Group>  
        </File>  
        <File Include="DataFile1.xml ">  
            <TargetPath>Data\DataFile1.xml</TargetPath>  
            <IsDataFile>true</IsDataFile>  
        </File>  
  
        <IconFile Include="Heart.ico"/>  
        <ConfigFile Include="app.config">  
            <TargetPath>SimpleWinApp.exe.config</TargetPath>  
        </ConfigFile>  
        <BaseManifest Include="app.manifest"/>  
    </ItemGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            AssemblyName="SimpleWinApp.exe"  
            AssemblyVersion="1.0.0.0"  
            ConfigFile="@(ConfigFile)"  
            Dependencies="@(Dependency)"  
            Description="TestApp"  
            EntryPoint="@(EntryPoint)"  
            Files="@(File)"  
            IconFile="@(IconFile)"  
            InputManifest="@(BaseManifest)"  
            OutputManifest="SimpleWinApp.exe.manifest">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
            AssemblyName="SimpleWinApp.application"  
            AssemblyVersion="1.0.0.0"  
            DeploymentUrl="$(DeployToUrl)"  
            Description="TestDeploy"  
            EntryPoint="@(ApplicationManifest)"  
            Install="true"  
            OutputManifest="SimpleWinApp.application"  
            Product="SimpleWinApp"  
            Publisher="Microsoft"  
            SupportUrl="$(SupportUrl)"  
            UpdateEnabled="true"  
            UpdateInterval="3"  
            UpdateMode="Background"  
            UpdateUnit="weeks">  
            <Output  
                ItemName="DeployManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `GenerateApplicationManifest` úkolů ke generování manifestu pro aplikaci Test.exe, odkazy na nativní součást Alpha.dll a izolované komponenty modelu COM Bravo.dll nativní.  
  
 Tento příklad vytvoří Test.exe.manifest, vytváření aplikace XCOPY nasadit pořízení výhodou registrace bezplatné COM.  
  
> [!NOTE]
>  V následujícím příkladu jsou předem připravené, aby bylo možné zaměřit na aspekty generování manifestu všechny binární soubory aplikace. Tento příklad vytvoří plně práce [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.  
  
```xml  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <File Include="Test.exe" />  
        <Dependency Include="Alpha.dll">  
            <AssemblyType>Native</AssemblyType>  
            <DependencyType>Install</DependencyType>  
        </Dependency>  
        <ComComponent Include="Bravo.dll" />  
    </ItemGroup>  
  
    <Target Name="Build">  
        <GenerateApplicationManifest  
            AssemblyName="Test.exe"  
            AssemblyVersion="1.0.0.0"  
            Dependencies="@(Dependency)"  
            Files="@(File)"  
            IsolatedComReferences="@(ComComponent)"  
            ManifestType="Native">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Generatedeploymentmanifest – úloha](../msbuild/generatedeploymentmanifest-task.md)   
 [Signfile – úloha](../msbuild/signfile-task.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)