---
title: Přidávání poznámek kódu ve službě jazyk starší | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- comments, supporting in language services [managed package framework]
- language services [managed package framework], commenting code
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5b573b464c26c3864cece697191cf03545ada779
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128717"
---
# <a name="commenting-code-in-a-legacy-language-service"></a>Přidávání poznámek kódu ve službě jazyk starší verze
Programovací jazyky obvykle obsahují i prostředky ke komentování nebo komentář ke kódu. Komentář je část textu, který obsahuje další informace o kód, ale se ignoruje při kompilaci nebo interpretace.  
  
 Třídy spravované balíčků framework (MPF) poskytuje podporu pro přidávání poznámek a uncommenting vybraný text.  
  
## <a name="comment-styles"></a>Styly komentář  
 Existují dvě obecné styly komentáře:  
  
1.  Komentáře řádku, kde je komentář na jeden řádek.  
  
2.  Komentáře bloku, kde komentář může zahrnovat více řádků.  
  
 Komentáře řádku obvykle mají počáteční znak (nebo znaky), při komentáře bloku mít počátečních a koncových znaků. Například v jazyce C#, komentář řádku začíná / /, a blok komentáře začíná / * a končí \*/.  
  
 Když uživatel vybere příkaz **výběru jako komentáře** z **upravit** -> **Upřesnit** nabídky, příkaz se směruje na <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> metodu <xref:Microsoft.VisualStudio.Package.Source> třídy. Když uživatel vybere příkaz **zrušte komentář u výběru**, příkaz se směruje na <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> metoda.  
  
## <a name="supporting-code-comments"></a>Podpora komentáře kódu  
 Máte komentáře jazyka služby podpory kódu pomocí `EnableCommenting` s názvem parametru <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> . Toto nastaví <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> vlastnost <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy. Další informace o nastavení jazyka servicce funkce najdete v tématu [registrace služby jazyk starší](../../extensibility/internals/registering-a-legacy-language-service1.md)).  
  
 Je nutné přepsat <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> metoda vrátí <xref:Microsoft.VisualStudio.Package.CommentInfo> struktura s komentář znaků pro svůj jazyk. C# – styl řádku komentář znaky jsou výchozí.  
  
### <a name="example"></a>Příklad  
 Tady je příklad implementace <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> metoda.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        public override CommentInfo GetCommentFormat() {  
            CommentInfo info = new CommentInfo();  
            info.LineStart       = "//";  
            info.BlockStart      = "/*";  
            info.BlockEnd        = "*/";  
            info.UseLineComments = true;  
            return info;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)   
 [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service1.md)