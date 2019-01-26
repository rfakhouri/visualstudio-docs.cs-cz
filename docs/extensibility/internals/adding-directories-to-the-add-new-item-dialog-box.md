---
title: Přidávání adresářů do přidat novou položku – dialogové okno | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 787eb0fd3cf865eb4b800c9470cf0c3d77d45975
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958391"
---
# <a name="add-directories-to-the-add-new-item-dialog-box"></a>Přidat adresářů do dialogového okna Přidat novou položku
Následující příklad kódu ukazuje, jak registrovat nová sada adresářů pro **přidat novou položku** dialogové okno. Adresáře pro **přidat novou položku** dialogové okno se liší pro každý projekt. Proto zaregistrován v adresářích **projekty** podklíč součástí **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects**.
  
## <a name="registry-script"></a>Skript registru  
  
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
  
 `%Template_Path%` Hodnota určuje úplnou cestu adresáře, který obsahuje šablony projektů. Tyto šablony může být buď *.vsz* soubory nebo soubory šablon typický ke klonování.  
  
 `SortPriority` Hodnota určuje prioritu třídění.  
  
## <a name="add-items-to-an-existing-project"></a>Přidat položky do existujícího projektu  
 Můžete také přidat položky do existujícího projektu. Třeba [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projektu, můžete přidat položky, které chcete  *\<kořenové > \Program Files\Microsoft \CSharpProjectItems\LocalProjectItems # Visual Studio\VC* složky. V takovém případě `%GUID_Project%` je identifikátor GUID pro projekt C# ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}).  
  
 Můžete také rozšířit existující projekt tím, že podtyp projektu. S podtyp projektu můžete rozšířit projektu, aniž byste museli napsat nový typ projektu. Další informace o podtypů projektů, naleznete v tématu [podtypů projektu](../../extensibility/internals/project-subtypes.md).  
  
## <a name="see-also"></a>Viz také:  
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Přidání položek do dialogových oken přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Přidat adresářů do dialogového okna Nový projekt](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)