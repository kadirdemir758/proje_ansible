# Node.js'in hafif bir sürümünü kullanıyoruz
FROM node:20-alpine

# Çalışma klasörümüzü belirliyoruz
WORKDIR /app

# Paket dosyalarını kopyalayıp kütüphaneleri kuruyoruz
COPY package*.json ./
RUN npm install

# Tüm kodları kopyalıyoruz
COPY . .

# Next.js projesini yayına hazırlıyoruz (Build)
RUN npm run build

# Uygulamanın çalışacağı portu açıyoruz
EXPOSE 3000

# Sunucuyu başlatıyoruz
CMD ["npm", "start"]