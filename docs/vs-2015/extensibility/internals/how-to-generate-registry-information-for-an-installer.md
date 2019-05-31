---
title: 'Postupy: Vygenerování informací registru pro instalační program | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
- VSPackages, registration manifests
ms.assetid: b1b41012-a777-4ccf-81a6-3b41f0e96583
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: be17b2f78048bd0e9c2052066796857dbeba2048
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435268"
---
# <a name="how-to-generate-registry-information-for-an-installer"></a>Postupy: Vygenerování informací registru pro instalační program
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nástroj RegPkg.exe lze použít ke generování manifestu registrace pro spravovaná VSPackage. Manifest může být zahrnut do instalačního balíčku Instalační služby systému Windows. RegPkg můžete také vygenerovat soubor, který může být zahrnut ve zdrojovém souboru instalace na základě [sady nástrojů XML Instalační služby systému Windows](http://go.microsoft.com/fwlink/?LinkId=62238).  
  
> [!IMPORTANT]
> RegPkg vygeneruje názvy cest, které jsou specifické pro váš vývojový systém, tak pokaždé, když používáte RegPkg, je nutné upravit výstupní použít příslušný instalační služby systému Windows ve formátu vlastnosti. Například by měla být hodnota InprocServer32 **[SystemFolder]mscoree.dll** a cesty používejte **[#filekey]** a **[$componentkey]** . Úprava výstupu tímto způsobem podporuje počítače s Windows nainstalovat na jinou jednotku nebo v jiném adresáři, názvy lokalizovaném adresáři a cesty, které uživatelé si můžou vybrat. Další informace najdete v tématu [formátu](http://go.microsoft.com/fwlink/?LinkId=71120) v sadě SDK Instalační služby systému Windows. Pokud je pro vaše vývojové systémové cesty dodržují konvence RegPkg – například souborů ID ve formátu název_*filename*– potřebujete provést méně změn.  
  
### <a name="to-create-a-registration-manifest"></a>K vytvoření manifestu registrace  
  
- Spustit RegPkg s **/RegFile** přepnout. Zadejte další přepínače, název výstupního souboru a cestu sady VSPackage.  
  
     Například na příkazovém řádku zadejte přibližně takto:  
  
    ```  
    [Visual Studio SDK installation path]\VisualStudioIntegration\Tools\Bin\RegPkg /regfile:MyRegFile.reg MyPackage.dll  
    ```  
  
### <a name="to-view-a-registration-manifest"></a>Chcete-li zobrazit registrace manifestu  
  
- Otevření manifestu registrace v libovolném textovém editoru.  
  
     V následujícím příkladu se registrace manifestu a vytvoří RegPkg pro IronPython jazyková služba:  
  
    ```  
    REGEDIT4  
  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\CodeExpansions]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\CodeExpansions\Python]  
    @="{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}"  
    "DisplayName"="131"  
    "IndexPath"="C:\\VSSDK80\\2006.07\\VisualStudioIntegration\\Samples\\IronPythonIntegration\\bin\\Release\\CodeSnippets\\SnippetsIndex.xml"  
    "LangStringId"="python"  
    "Package"="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}"  
    "ShowRoots"=dword:00000000  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\CodeExpansions\Python\ForceCreateDirs]  
    "Python"="C:\\VSSDK80\\2006.07\\VisualStudioIntegration\\Samples\\IronPythonIntegration\\bin\\Release\\CodeSnippets\\Snippets\\;%MyDocs%\Code Snippets\Python\My Code Snippets\"  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\CodeExpansions\Python\Paths]  
    "Python"="C:\\VSSDK80\\2006.07\\VisualStudioIntegration\\Samples\\IronPythonIntegration\\bin\\Release\\CodeSnippets\\Snippets\\;%MyDocs%\Code Snippets\Python\My Code Snippets\"  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Packages]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Packages\{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}]  
    @="Microsoft.Samples.VisualStudio.IronPythonLanguageService.PythonPackage, IronPython.LanguageService, Version=1.0.2373.36479, Culture=neutral, PublicKeyToken=null"  
    "InprocServer32"="C:\\WINNT\\system32\\mscoree.dll"  
    "Class"="Microsoft.Samples.VisualStudio.IronPythonLanguageService.PythonPackage"  
    "Assembly"="IronPython.LanguageService, Version=1.0.2373.36479, Culture=neutral, PublicKeyToken=null"  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\File Extensions]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\File Extensions\.py]  
    @="{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}"  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\Language Services]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Languages\Language Services\Python]  
    @="{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}"  
    "Package"="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}"  
    "LangResID"=dword:00000064  
    "ShowMatchingBrace"=dword:00000001  
    "CodeSense"=dword:00000001  
    "MatchBraces"=dword:00000001  
    "EnableCommenting"=dword:00000001  
    "ShowCompletion"=dword:00000001  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Packages]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Packages\{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}]  
    "ID"=dword:00000001  
    "MinEdition"="standard"  
    "ProductVersion"="1.0"  
    "ProductName"="Visual Studio Integration of IronPython Language Service"  
    "CompanyName"="Microsoft Corporation"  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Services]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Services\{923b4811-26e4-4347-ac8a-244762798e1c}]  
    @="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}"  
    "Name"="IPythonLibraryManager"  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Services]  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Services\{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}]  
    @="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}"  
    "Name"="Python"  
  
    ```  
  
### <a name="to-create-a-windows-installer-xml-toolset-include-file"></a>Chcete-li vytvořit sadu nástrojů XML Instalační služby systému Windows soubor k zahrnutí  
  
- Spustit RegPkg s **/wixfile** přepnout. Zadejte další přepínače, název výstupního souboru a cestu sady VSPackage.  
  
     Například na příkazovém řádku zadejte přibližně takto:  
  
    ```  
    [Visual Studio SDK installation path]\VisualStudioIntegration\Tools\Bin\RegPkg /codebase /wixfile:IronPython.LanguageService.wxi ..\bin\Release\IronPython.LanguageService.dll  
    ```  
  
### <a name="to-view-a-windows-installer-xml-toolset-include-file"></a>Chcete-li zobrazit sadu nástrojů XML Instalační služby systému Windows soubor k zahrnutí  
  
- Otevřít sada nástrojů XML Instalační služby systému Windows zahrnout soubor do libovolného textového editoru.  
  
     V následujícím příkladu je zahrnout soubor, který vytvoří RegPkg pro IronPython jazyková služba:  
  
    ```  
    <Include>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Languages\IntellisenseProviders\IronPythonCodeProvider">  
        <Registry Name="GUID" Value="{9c1807ea-d222-4775-afa8-c092c580e451}" Type="string" />  
        <Registry Name="AddItemLanguageName" Value="Iron Python" Type="string" />  
        <Registry Name="DefaultExtension" Value=".py" Type="string" />  
        <Registry Name="ShortLanguageName" Value="IronPython;Python" Type="string" />  
        <Registry Name="TemplateFolderName" Value="IronPython" Type="string" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Languages\CodeExpansions\Python" Value="{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}" Type="string">  
        <Registry Name="DisplayName" Value="131" Type="string" />  
        <Registry Name="IndexPath" Value="C:\\VSSDK80\\2006.08\\VisualStudioIntegration\\Samples\\IronPythonIntegration\\Setup\\[$ComponentPath]\\CodeSnippets\\SnippetsIndex.xml" Type="string" />  
        <Registry Name="LangStringId" Value="python" Type="string" />  
        <Registry Name="Package" Value="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}" Type="string" />  
        <Registry Name="ShowRoots" Value="0" Type="integer" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Languages\CodeExpansions\Python\ForceCreateDirs">  
        <Registry Name="Python" Value="C:\\VSSDK80\\2006.08\\VisualStudioIntegration\\Samples\\IronPythonIntegration\\Setup\\[$ComponentPath]\\CodeSnippets\\Snippets\\;%MyDocs%\Code Snippets\Python\My Code Snippets\" Type="string" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Languages\CodeExpansions\Python\Paths">  
        <Registry Name="Python" Value="C:\\VSSDK80\\2006.08\\VisualStudioIntegration\\Samples\\IronPythonIntegration\\Setup\\[$ComponentPath]\\CodeSnippets\\Snippets\\;%MyDocs%\Code Snippets\Python\My Code Snippets\" Type="string" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Languages\File Extensions\.py" Value="{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}" Type="string" />  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Languages\Language Services\Python" Value="{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}" Type="string">  
        <Registry Name="Package" Value="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}" Type="string" />  
        <Registry Name="LangResID" Value="100" Type="integer" />  
        <Registry Name="ShowCompletion" Value="1" Type="integer" />  
        <Registry Name="ShowMatchingBrace" Value="1" Type="integer" />  
        <Registry Name="CodeSense" Value="1" Type="integer" />  
        <Registry Name="MatchBraces" Value="1" Type="integer" />  
        <Registry Name="EnableCommenting" Value="1" Type="integer" />  
        <Registry Name="DefaultToInsertSpaces" Value="1" Type="integer" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Packages\{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}" Value="Microsoft.Samples.VisualStudio.IronPythonLanguageService.PythonPackage, IronPython.LanguageService, Version=1.0.2394.27719, Culture=neutral, PublicKeyToken=null" Type="string">  
        <Registry Name="InprocServer32" Value="[SystemFolder]mscoree.dll" Type="string" />  
        <Registry Name="Class" Value="Microsoft.Samples.VisualStudio.IronPythonLanguageService.PythonPackage" Type="string" />  
        <Registry Name="CodeBase" Value="[#File_IronPython.LanguageService.dll]" Type="string" />  
        <Registry Name="ID" Value="1" Type="integer" />  
        <Registry Name="MinEdition" Value="standard" Type="string" />  
        <Registry Name="ProductVersion" Value="1.0" Type="string" />  
        <Registry Name="ProductName" Value="Visual Studio Integration of IronPython Language Service" Type="string" />  
        <Registry Name="CompanyName" Value="Microsoft Corporation" Type="string" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\CLSID\{9c1807ea-d222-4775-afa8-c092c580e451}" Value="Microsoft.Samples.VisualStudio.IronPythonLanguageService.PythonIntellisenseProvider" Type="string">  
        <Registry Name="InprocServer32" Value="[SystemFolder]mscoree.dll" Type="string" />  
        <Registry Name="Class" Value="Microsoft.Samples.VisualStudio.IronPythonLanguageService.PythonIntellisenseProvider" Type="string" />  
        <Registry Name="CodeBase" Value="[#File_IronPython.LanguageService.dll]" Type="string" />  
        <Registry Name="ThreadingModel" Value="Both" Type="string" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Services\{923b4811-26e4-4347-ac8a-244762798e1c}" Value="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}" Type="string">  
        <Registry Name="Name" Value="IPythonLibraryManager" Type="string" />  
      </Registry>  
  
      <Registry Root="HKLM" Key="Software\Microsoft\VisualStudio\8.0\Services\{ae8ce01a-b3ff-4c19-8c80-54669c197f2c}" Value="{1b05e2b4-7c21-4f63-910e-29fe55eb5f8b}" Type="string">  
        <Registry Name="Name" Value="Python" Type="string" />  
      </Registry>  
    </Include>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Registrace balíčků VSPackage](registering-vspackages.md)   
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)
