# Node.js'in hafif bir sürümünü kullanıyoruz
FROM node:20-alpine

# Çalışma klasörümüzü belirliyoruz
WORKDIR /app

# Paket dosyalarını kopyalayıp kütüphaneleri kuruyoruz
COPY package*.json ./
RUN npm install

# Tüm kodları kopyalıyoruz
COPY . .

# ── İŞTE SİHİRLİ DOKUNUŞ BURADA ──
# AWS API Gateway adresimizi Frontend'in içine kalıcı olarak kazıyoruz
ENV NEXT_PUBLIC_API_URL=http://13.48.57.178:8000/api/v1/trips

# Next.js projesini yayına hazırlıyoruz (Build)
RUN npm run build

# Uygulamanın çalışacağı portu açıyoruz
EXPOSE 3000

# Sunucuyu başlatıyoruz
CMD ["npm", "start"]