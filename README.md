Kişiselleştirilmiş Yapay Zeka: Araba Uzmanı Model (Fine-Tuning)
Bu proje, OSTİM Teknik Üniversitesi bünyesinde yürütülen Büyük Dil Modelleri (YZM 423) dersi kapsamında, açık kaynaklı bir dil modelinin belirli bir alanda (otomotiv/arabalar) uzmanlaşması için ince ayar (fine-tuning) yapılması sürecini içermektedir.

📝 Proje Özeti
Bu çalışma kapsamında, genel amaçlı bir dil modeli olan Llama-3.1-8B (veya Mistral), otomotiv sektörüne ait teknik dokümanlar ve akademik makaleler kullanılarak özelleştirilmiştir. Modelin eğitiminde Unsloth kütüphanesi kullanılarak bellek verimliliği ve eğitim hızı maksimize edilmiştir.

Proje Ekibi

Öğrenci: Mustafa ŞEN 


Öğrenci No: 220212030 


Öğretim Görevlisi: Dr. Murat ŞİMŞEK 


Yıl: 2025 

🚀 Kullanılan Teknolojiler ve Araçlar

Ana Model: Llama 3.1 8B / Mistral-7B-v0.3 
+1


Eğitim Yöntemi: LoRA (Low-Rank Adaptation) ve 4-bit Quantization 
+1


Kütüphaneler: Unsloth, PEFT, TRL, Bitsandbytes 
+2


Platformlar: Google Colab, Hugging Face, Ollama 
+2

📊 Veri Seti Hazırlığı
Modelin otomotiv alanında uzmanlaşması için şu adımlar izlenmiştir:


Veri Kaynakları: Akademik makaleler ve teknik PDF/Word dokümanları ana kaynak olarak seçilmiştir.


Formatlama: Veriler, Llama modellerinin talimat takip yeteneğini artırmak için Alpaca Formatına dönüştürülmüştür.


Yapı: Her veri örneği Instruction, Input ve Response bileşenlerinden oluşturulmuştur.


Hugging Face: Hazırlanan veri seti resvan40/cardata adresine yüklenmiştir.

🏗️ Model Eğitim (Fine-Tuning) Süreci
Eğitim sürecinde aşağıdaki konfigürasyonlar kullanılmıştır:


Sıkıştırma: 4-bit quantization kullanılarak bellek tüketimi düşürülmüştür.


LoRA Parametreleri: r = 16, lora_alpha = 16, target_modules olarak QKV ve MLP katmanları seçilmiştir.


Eğitim Ayarları: 60 adım (step), 12 epoch ve 2e-4 öğrenme oranı.
+1


Sonuç: Eğitim sonunda loss (kayıp) değeri 1.6'dan 0.8'e düşerek modelin öğrenme sağladığı doğrulanmıştır.

💾 Kurulum ve Kullanım
Ollama ile Çalıştırma
Eğitilen model GGUF formatına dönüştürülmüş ve Ollama üzerinden erişilebilir hale getirilmiştir.





hugginface model linki: https://huggingface.co/resvan40/carmodel/tree/main
hugginface veriseti linki: https://huggingface.co/datasets/resvan40/cardata
