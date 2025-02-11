---
title: Přidávání adresářů do přidat novou položku – dialogové okno | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f370d208cb8f7aad88f806983983ccee9f584625
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203932"
---
# <a name="adding-directories-to-the-add-new-item-dialog-box"></a>Přidávání adresářů do dialogového okna Přidat novou položku
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následující příklad kódu ukazuje, jak registrovat nová sada adresářů pro **přidat novou položku** dialogové okno. Adresáře pro **přidat novou položku** dialogové okno se liší pro každý projekt. Proto jsou registrovány adresáře v podklíči projekty v \<HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects >:  
  
## <a name="the-registry-script"></a>Skript registru  
  
```  
NoRemove Projects  
{  
  NoRemove %GUID_Project%  
  {  
    NoRemove AddItemTemplates  
    {  
      NoRemove TemplateDirs  
      {  
        ForceRemove %CLSID_Package%  
        {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
          {  
            val TemplatesDir = s '%Template_Path%'     
            val SortPriority = d 2000  
          }  
        }  
      }  
    }  
  }  
}  
```  
  
 Hodnota Template_Path Určuje úplnou cestu adresáře, který obsahuje šablony projektů. Šablony můžou být .vsz soubory nebo soubory šablon typický ke klonování.  
  
 Hodnota SortPriority určuje prioritu třídění.  
  
## <a name="adding-items-to-an-existing-project"></a>Přidávání položek do existujícího projektu  
 Můžete také přidat položky do existujícího projektu. Třeba [!INCLUDE[csprcs](../../includes/csprcs-md.md)] projektu, můžete přidat položky, které chcete \<kořenové > složku \VC#\CSharpProjectItems\LocalProjectItems \Program Files\Microsoft Visual Studio. V tomto případě `%GUID_Project%` je identifikátor GUID pro projekt C# ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}).  
  
 Můžete také rozšířit existující projekt tím, že podtyp projektu. S podtyp projektu můžete rozšířit projektu, aniž byste museli napsat nový typ projektu. Další informace o podtypů projektů, naleznete v tématu [podtypů projektů](../../extensibility/internals/project-subtypes.md).  
  
## <a name="see-also"></a>Viz také  
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Přidávání položek do přidání nové položky v dialogových oknech](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Přidávání adresářů do dialogového okna Nový projekt](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)
