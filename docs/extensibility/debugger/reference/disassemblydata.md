---
title: DisassemblyData | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DisassemblyData
helpviewer_keywords:
- DisassemblyData structure
ms.assetid: 10e70aa7-9381-40d3-bdd1-d2cad78ef16c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0313ddccb7c6f7c4f09d3e4836c04283dd5bfc17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="disassemblydata"></a>DisassemblyData
Popisuje jeden zpětný překlad instrukce pro integrované vývojové prostředí (IDE) k zobrazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct tagDisassemblyData {   
   DISASSEMBLY_STREAM_FIELDS dwFields;  
   BSTR                      bstrAddress;  
   BSTR                      bstrAddressOffset;  
   BSTR                      bstrCodeBytes;  
   BSTR                      bstrOpcode;  
   BSTR                      bstrOperands;  
   BSTR                      bstrSymbol;  
   UINT64                    uCodeLocationId;  
   TEXT_POSITION             posBeg;  
   TEXT_POSITION             posEnd;  
   BSTR                      bstrDocumentUrl;  
   DWORD                     dwByteOffset;  
   DISASSEMBLY_FLAGS         dwFlags;  
} DisassemblyData;  
```  
  
```csharp  
public struct DisassemblyData {   
   public uint          dwFields;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrCodeBytes;  
   public string        bstrOpcode;  
   public string        bstrOperands;  
   public string        bstrSymbol;  
   public ulong         uCodeLocationId;  
   public TEXT_POSITION posBeg;  
   public TEXT_POSITION posEnd;  
   public string        bstrDocumentUrl;  
   public uint          dwByteOffset;  
   public uint          dwFlags;  
};  
```  
  
## <a name="members"></a>Členové  
 `dwFields`  
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) konstanta, která určuje pole, která jsou vyplněna.  
  
 `bstrAddress`  
 Adresa jako posun vůči některé počáteční bod (obvykle začátek přidružené funkce).  
  
 `bstrCodeBytes`  
 Počet bajtů kód pro tento pokyn.  
  
 `bstrOpcode`  
 Operační kód pro tento pokyn.  
  
 `bstrOperands`  
 Operandy pro tento pokyn.  
  
 `bstrSymbol`  
 Název symbolu, pokud existuje, přidružené k adrese (veřejné symbol, popisek a tak dále).  
  
 `uCodeLocationId`  
 Identifikátor kód umístění pro tento rozložit řádku. Pokud adresu kontextu kód jeden řádek je větší než adresu kód kontextu jiného, pak zpětně přeložený kód umístění identifikátor první také být větší než druhý identifikátor kód umístění.  
  
 `posBeg`  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) odpovídající na pozici v dokumentu, kde začíná data zpětný překlad.  
  
 `posEnd`  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) odpovídající na pozici v dokumentu, které končí data zpětný překlad.  
  
 `bstrDocumentUrl`  
 Pro text dokumenty, které může být reprezentován jako názvy souborů `bstrDocumentUrl` vyplněno pole název souboru, kde můžete najít zdroj, formátu `file://file name`.  
  
 Pro text dokumenty, které nelze reprezentovat jako názvy souborů `bstrDocumentUrl` je jedinečný identifikátor pro dokument, a musí implementovat modul ladění [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md) metoda.  
  
 Toto pole může obsahovat také další informace o kontrolní součty. Podrobnosti najdete v části poznámky.  
  
 `dwByteOffset`  
 Počet bytů, které je pokyn od začátku řádek kódu.  
  
 `dwFlags`  
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md) konstanta, která určuje, které příznaky jsou aktivní.  
  
## <a name="remarks"></a>Poznámky  
 Každý `DisassemblyData` struktura popisuje jeden instrukce zpětný překlad. Vrátí pole těchto struktur [čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) metoda.  
  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura se používá pro založený na textu pouze dokumenty. Rozsah zdrojového kódu pro tento pokyn vyplní se jenom pro první pokyn vygenerovat z příkazu nebo řádku, například když `dwByteOffset == 0`.  
  
 Kód, můžete získat pro dokumenty, které jsou bez zdůraznění, kontextu dokumentu a `bstrDocumentUrl` pole musí mít hodnotu null. Pokud `bstrDocumentUrl` pole je stejný jako `bstrDocumentUrl` pole v předchozím `DisassemblyData` element pole a pak nastavte `bstrDocumentUrl` na hodnotu null.  
  
 Pokud `dwFlags` má pole `DF_DOCUMENT_CHECKSUM` příznak nastaven, pak další kontrolní součet informace následuje řetězec, na kterou odkazuje `bstrDocumentUrl` pole. Konkrétně po ukončení řetězec null existuje následuje identifikátor GUID identifikace kontrolního součtu algoritmus, který je pak následuje 4bajtové hodnotu, která určuje počet bajtů v kontrolního součtu a který pak následují kontrolní součet bajtů. Podívejte se na příklad v tomto tématu o tom, jak kódování a dekódování toto pole v [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)].  
  
## <a name="example"></a>Příklad  
 `bstrDocumentUrl` Pole může obsahovat další informace než řetězec, pokud `DF_DOCUMENT_CHECKSUM` je nastavený příznak. Proces vytváření a čtení tento řetězec s kódováním je jednoduchý v [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)]. Ale v [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)], je další věci. Pro ty, kteří jsou zvědaví, následující příklad ukazuje jeden způsob, jak vytvořit řetězec s kódováním z [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)] a dá k dekódování řetězec s kódováním v [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)].  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
namespace MyNamespace  
    class MyClass  
    {  
        string EncodeData(string documentString,  
                          Guid checksumGuid,  
                          byte[] checksumData)  
        {  
            string returnString = documentString;  
  
            if (checksumGuid == null || checksumData == null)  
            {  
                // Nothing more to do. Just return the string.  
                return returnString;  
            }  
  
            returnString += '\0'; // separating null value  
  
            // Add checksum GUID to string.  
            byte[] guidDataArray  = checksumGuid.ToByteArray();  
            int    guidDataLength = guidDataArray.Length;  
            IntPtr pBuffer        = Marshal.AllocCoTaskMem(guidDataLength);  
            for (int i = 0; i < guidDataLength; i++)  
            {  
                Marshal.WriteByte(pBuffer, i, guidDataArray[i]);  
            }  
            // Copy guid data bytes to string as wide characters.  
            // Assumption: sizeof(char) == 2.  
            for (int i = 0; i < guidDataLength; i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
  
            // Add checksum count (a 32-bit value).  
            Int32 checksumCount = checksumData.Length;  
            Marshal.StructureToPtr(checksumCount, pBuffer, true);  
            for (int i = 0; i < sizeof(Int32) / sizeof(char); i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
  
            // Add checksum data.  
            pBuffer = Marshal.AllocCoTaskMem(checksumCount);  
            for (int i = 0; i < checksumCount; i++)  
            {  
                Marshal.WriteByte(pBuffer, i, checksumData[i]);  
            }  
            for (int i = 0; i < checksumCount / sizeof(char); i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
            Marshal.FreeCoTaskMem(pBuffer);  
  
            return returnString;  
        }  
  
        void DecodeData(    string encodedString,  
                        out string documentString,  
                        out Guid   checksumGuid,  
                        out byte[] checksumData)  
       {  
           documentString = String.Empty;  
           checksumGuid = Guid.Empty;  
           checksumData = null;  
  
           IntPtr pBuffer = Marshal.StringToBSTR(encodedString);  
           if (null != pBuffer)  
           {  
               int bufferOffset = 0;  
  
               // Parse string out.  String is assumed to be Unicode.  
               documentString = Marshal.PtrToStringUni(pBuffer);  
               bufferOffset += (documentString.Length + 1) * sizeof(char);  
  
               // Parse Guid out.  
               // Read guid bytes from buffer and store in temporary  
               // buffer that contains only the guid bytes. Then the  
               // Marshal.PtrToStructure() can work properly.  
               byte[] guidDataArray  = checksumGuid.ToByteArray();  
               int    guidDataLength = guidDataArray.Length;  
               IntPtr pGuidBuffer    = Marshal.AllocCoTaskMem(guidDataLength);  
               for (int i = 0; i < guidDataLength; i++)  
               {  
                   Marshal.WriteByte(pGuidBuffer, i,  
                                     Marshal.ReadByte(pBuffer, bufferOffset + i);  
               }  
               bufferOffset += guidDataLength;  
               checksumGuid = (Guid)Marshal.PtrToStructure(pGuidBuffer, typeof(Guid));  
               Marshal.FreeCoTaskMem(pGuidBuffer);  
  
              // Parse out the number of checksum data bytes (always 32-bit value).  
              int dataCount = Marshal.ReadInt32(pBuffer, bufferOffset);  
              bufferOffset += sizeof(Int32);  
  
              // Parse out the checksum data.  
              checksumData = new byte[dataCount];  
              for (int i = 0; i < dataCount; i++)  
              {  
                  checksumData[i] = Marshal.ReadByte(pBuffer, bufferOffset + i);  
              }  
           }  
       }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [Pro čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)   
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)