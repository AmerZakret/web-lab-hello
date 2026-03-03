# CSS Kararları

## 1. Breakpoint Seçimi

- **640px (Tablet)**: Mobil cihazlardan tablet boyutuna geçişte padding ve section boşluklarını artırdım.
- **1024px (Masaüstü)**: Main container'a max-width ve proje grid'ine 3 sütun tanımladım.

Bu breakpoint'ler, içeriğin 375px mobil ekrandan 1920px masaüstü ekrana kadar sorunsuz çalışmasını sağlıyor.

## 2. Layout Tercihleri

- **Header için Flexbox**: Navigasyon öğelerini yatay olarak hizalamak ve mobilde dikey yapmak için ideal.
- **Proje kartları için Grid**: `repeat(auto-fit, minmax(280px, 1fr))` ile responsive bir ızgara sağladım. Media query yazmadan ekran boyutuna göre sütun sayısı otomatik ayarlanıyor.
- **auto-fit kullanımı**: Boş sütunları daraltarak kartların genişlemesini sağlıyor. Mobilde 1 sütun, tablet'te 2, masaüstünde 3 sütun şeklinde otomatik düzenleniyor.

## 3. Design Tokens

- **Renk paleti**: Erişilebilirlik göz önünde tutarak yüksek kontrast sağlayan renkler seçtim (#1E3A8A ana renk, #2563EB vurgu).
- **Spacing skalası**: 0.25rem'den 4rem'e kadar 7 seviyeli skalı oluşturdum. Tutarlı boşluk yönetimi sağlıyor.
- **Fluid typography**: `clamp(min, preferred, max)` formülü kullanarak yazı boyutu minimum (0.8rem) ve maksimum (3.5rem) sınırlar içinde viewport genişliğine göre akıcı şekilde değişiyor.

## 4. Responsive Stratejiler

- **Mobile-first yaklaşım**: Taban stil mobil için yazıldı, `@media (min-width: ...)` ile daha büyük ekranlar için iyileştirmeler eklendi.
- **Değişen elemanlar**:
  - Button genişliği: Mobilde 100%, tablet'ten sonra otomatik
  - Section padding: Mobilde var(--space-xl) var(--space-md), tablet'te var(--space-2xl) var(--space-xl)
  - Grid sütunları: Auto-fit mobilde, 3 sütun masaüstünde
- **Görsel yönetimi**: `max-width: 100%`, `height: auto`, `object-fit: cover` ile görseller tüm ekran boyutlarında sorunsuz görünüyor.

## 5. Erişilebilirlik

- Focus indicator (2px solid outline) tüm interactive elemanlar için korundu.
- Skip link erişilebilirlik için pozisyonlandı.
- Semantik HTML ve ARIA etiketleri LAB-2'den devam ettirildi.
