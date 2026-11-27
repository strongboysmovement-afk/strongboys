# Хүчирхэг хөвгүүд — вэб сайт

Энэ repository нь үндсэн танилцуулгын сайт болон гишүүдийн цахим буланг агуулна.

## Сайтын хаяг
- Үндсэн сайт: https://strongboysmovement-afk.github.io/strongboys/
- Гишүүдийн булан: https://strongboysmovement-afk.github.io/strongboys/members.html

## GitHub Pages-ийг нэг удаа идэвхжүүлэх
Файлууд `main` салбарын үндсэн хавтсанд байрлаж байгаа. Сайт нээгдэхгүй байвал GitHub Pages нийтлэлт идэвхжээгүй байж болно.

1. Энэ тохиргооны хуудсыг нээнэ: https://github.com/strongboysmovement-afk/strongboys/settings/pages
2. **Build and deployment** хэсэгт **Deploy from a branch** сонгоно.
3. Branch: **main**, Folder: **/(root)** сонгоно.
4. **Save** дарна.
5. GitHub Pages анхны нийтлэлээ дуусгах хүртэл хэсэг хүлээгээд дээрх сайтын холбоосыг дахин нээнэ.

## Хуудаснууд
- `index.html` — хөтөлбөрийн танилцуулга, чиглэл, үйл ажиллагаа, мэдээ.
- `members.html` — гишүүний бүртгэл/нэвтрэлт, гишүүний код, гишүүнчлэлийн төлөв, зарлал, санал асуулга, Google Forms, арга хэмжээ, админ удирдлага.
- `.nojekyll` — GitHub Pages-д статик файлуудыг зөв нийтлэхэд тусална.

## Админ эрхийг эхлүүлэх
1. Гишүүдийн буланд эхний эзэмшигчийн бүртгэл үүсгэнэ.
2. И-мэйлээ баталгаажуулж нэвтэрнэ.
3. Эхний админ эрхийг Supabase Dashboard-ийн SQL Editor-оос зөвхөн эзэмшигчийн өөрийн бүртгэлд олгоно.
4. Дараа нь админ хэсгээс бусад гишүүдийн хүсэлтийг баталгаажуулна.

SQL жишээ (имэйлээ зөвхөн өөрийн баталгаажсан бүртгэлийн имэйлээр солино):
```sql
update public.profiles p
set role = 'admin', membership_status = 'approved'
from auth.users u
where p.id = u.id
  and lower(u.email) = lower('OWNER_EMAIL_HERE');
```

## Нууцлал
- HTML/JavaScript-д зөвхөн Supabase publishable key ашиглана.
- Supabase service-role/secret key-г сайт руу хэзээ ч оруулахгүй.
- Бүртгэл шинэ хэрэглэгчдэд анхдагчаар pending төлөвтэй.
- Гишүүдийн мэдээлэл, зарлал, санал асуулга болон бүртгэлд Supabase Row Level Security ашиглана.

## Брэндийн лого
Одоогийн эх кодод түр “ХХ” тэмдэглэгээ байна. Албан ёсны логоны эх зураг энэ repository-д хараахан байхгүй тул түүнийг оруулахад эх файлыг нэмж өгөх шаардлагатай.
