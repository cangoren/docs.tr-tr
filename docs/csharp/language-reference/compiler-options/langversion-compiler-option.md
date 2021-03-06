---
title: "-langversion (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d3d59f63102ccf3c1d54e4028635c8daad56164
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="langversion-c-compiler-options"></a>/langversion (C# Derleyici Seçenekleri)
Derleyicinin yalnızca seçilen C# dil belirtimi dahil sözdizimini kabul etmesine neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```console  
/langversion:option  
```  
  
## <a name="arguments"></a>Arguments  
 `option`  
 Aşağıdaki değerler geçerlidir:  
  
|Seçenek|Açıklama|  
|------------|-------------|  
|default|Derleyici destekleyebileceği tüm geçerli dil söz dizimini kabul eder. <sup id="TDefault">[Varsayılan](#FDefault)</sup>| 
|ISO-1|ISO/IEC 23270:2003 C# (1.0/1.1) dahil sözdizimi derleyici kabul <sup id="TISO1"> [ISO1](#FISO1)</sup>|  
|ISO-2|ISO/IEC 23270:2006 C# (2.0) dahil sözdizimi derleyici kabul <sup id="TISO2"> [ISO2](#FISO2)</sup>|
|3|C# 3.0 dahil ya da daha düşük olan sözdizimi derleyici kabul <sup id="TCS3"> [CS3](#FCS3)</sup>|
|4|Derleyici dahil C# 4.0 veya daha düşük olan sözdizimini kabul eder <sup id="TCS4"> [CS4](#FCS4)</sup>|
|5|Derleyici dahil C# 5.0 veya daha düşük olan sözdizimini kabul eder <sup id="TCS5"> [CS5](#FCS5)</sup>|
|6|Derleyici dahil C# 6. 0 veya daha düşük olan sözdizimini kabul eder <sup id="TCS6"> [CS6](#FCS6)</sup>|
|7|Derleyici dahil C# 7. 0 veya daha düşük olan sözdizimini kabul eder <sup id="TCS7"> [CS7](#FCS7)</sup>|
|en son|Derleyici destekleyebileceği tüm geçerli dil söz dizimini kabul eder. <sup id="TLatest">[En son](#FLatest)</sup>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a>Açıklamalar  
 C# uygulamanız tarafından başvurulan meta veri değil tabi **/langversion** derleyici seçeneği.  
  
 C# Derleyici her sürümü uzantıları dil belirtimi içerdiğinden **/langversion** Derleyici önceki bir sürümünü eşdeğer işlevselliğini sağlamaz.  
 
 C# sürüm güncelleştirmelerini ile ana .net Framework sürümleri genellikle çakıştığı olsa da, ayrıca, özellikleri ve yeni sözdizimini mutlaka bu belirli framework sürümüne bağlı olmak zorunda değildir. Yeni özelliklerin yanı sıra C# düzeltme de serbest yeni bir derleyici güncelleştirme kesinlikle gerektirir, ancak her belirli özellik kendi minimum .net API veya alt düzey çerçeveleri tarafından üzerinde çalışmasına izin verebilir ortak dil çalışma zamanı gereksinimleri vardır. NuGet paketlerini veya diğer kitaplıkları dahil olmak üzere.
  
 Hangi **/langversion** ayarını kullanın, .exe veya .dll dosyası oluşturmak için geçerli ortak dil çalışma zamanı sürümünü kullanacak. Tek istisnası arkadaş derlemeleri ve [/moduleassemblyname (C# derleyici seçeneği)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), hangi altında çalışan **/langversion:ISO-1**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellikleri** sayfası.  
  
2.  Tıklatın **yapı** özellik sayfası.  
  
3.  Tıklatın **Gelişmiş** düğmesi.  
  
4.  Değiştirme **dil sürümü** özelliği.  
  
 Bu derleyici seçeneği programlı olarak nasıl ayarlanacağı hakkında daha fazla bilgi için bkz: <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/index.md)  
 [Proje ve Çözüm Özelliklerini Yönetme](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a>C# Dil Belirtimi
 [C# dil belirtimi başvurusu](../../../csharp/language-reference/language-specification/index.md) : .NET Foundation  
 C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) bilgi teknolojisi--C# dil belirtimi: ISO Kataloğu  
 C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) bilgi teknolojisi--C# dil belirtimi: ISO Kataloğu  
 C# 2.0 [c042926_ISO_IEC_23270_2006 (E) .zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) PDF biçimli ISO/IEC 23270:2006: ISO serbestçe kullanılabilir standartları  
 C# 3.0 [CSharp dil Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# dil belirtimi sürüm 3.0: Microsoft Corporation'ın  
 C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) standart ECMA 334 4 Edition    
 C# 5.0 [CSharp dil Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# dil belirtimi Sürüm 5.0: Microsoft Corporation'ın  
 C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# dil belirtimi sürüm 6 - resmi olmayan taslak: .NET Foundation  
 C# 7.0 (şu anda kullanılabilir)  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Tüm dil özellikleri desteklemek için gereken en düşük derleyici sürümü   
[↩](#TDefault)<a name="FDefault">varsayılan</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/derleme araçları .net 2002 veya ile birlikte gelen .net Framework 1.0 derleyici     
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/derleme araçları 2005 veya ile birlikte gelen .net Framework 2.0 derleyici    
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/derleme araçları 2008 ya da ile birlikte gelen .net Framework 3.5 derleyici    
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/derleme araçları 2010 veya ile birlikte gelen .net Framework 4.0 derleyici    
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/derleme araçları 2012 ya da ile birlikte gelen .net Framework 4.5 derleyici    
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/derleme araçları 2015    
[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">son</a>: Microsoft Visual Studio/derleme araçları 2017   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
