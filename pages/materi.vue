<template>
    <div class="h-screen relative overflow-y-auto">
        <img src="assets/img/6.webp" alt="Background" class="w-full h-full object-cover fixed inset-0">

        <div class="relative min-h-screen py-6 px-4">
            <NuxtLink to="/" class="fixed top-4 left-4 p-2 bg-white hover:bg-white rounded-full 
                transition-all duration-300 backdrop-blur-sm group z-10">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5"
                    stroke="currentColor"
                    class="w-6 h-6 text-green-700 group-hover:scale-110 transition-transform duration-300">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18" />
                </svg>
            </NuxtLink>

            <div class="max-w-3xl mx-auto space-y-6">
                <div class="bg-white/90 backdrop-blur-sm p-6 rounded-xl shadow-xl">
                    <h1 class="text-2xl md:text-3xl font-bold text-emerald-800 mb-6">
                        Komponen Ekosistem Lingkungan
                    </h1>

                    <div class="space-y-6 text-gray-700 leading-relaxed">
                        <p>
                            Ekosistem adalah sistem alam yang terdiri dari dua komponen utama yang saling berinteraksi:
                            komponen biotik (makhluk hidup) dan komponen abiotik (benda tak hidup). Mari kita pelajari
                            lebih detail tentang kedua komponen ini.
                        </p>

                        <p>
                            <span class="font-semibold text-emerald-800">Komponen Biotik</span> meliputi semua makhluk
                            hidup dalam ekosistem. Contohnya seperti tumbuhan yang berperan sebagai produsen (penghasil
                            makanan), hewan sebagai konsumen (pemakan), dan jamur sebagai pengurai. Misalnya di kebun,
                            kita bisa menemukan pohon mangga (produsen), ulat yang memakan daun (konsumen), dan jamur
                            yang menguraikan daun yang jatuh (dekomposer).
                        </p>

                        <p>
                            <span class="font-semibold text-emerald-800">Komponen Abiotik</span> adalah komponen tak
                            hidup yang mendukung kehidupan dalam ekosistem. Air, udara, tanah, cahaya matahari, suhu,
                            dan kelembaban adalah contoh komponen abiotik. Tanpa komponen ini, makhluk hidup tidak
                            dapat bertahan. Misalnya, tumbuhan membutuhkan sinar matahari untuk fotosintesis, air
                            untuk pertumbuhan, dan tanah sebagai media tumbuh.
                        </p>

                        <p>
                            <span class="font-semibold text-emerald-800">Interaksi Antar Komponen</span> sangat penting
                            dalam menjaga keseimbangan ekosistem. Contohnya, kupu-kupu membantu penyerbukan bunga,
                            sementara bunga menyediakan nektar untuk kupu-kupu. Burung pemakan serangga membantu
                            mengendalikan populasi serangga, sekaligus mendapat sumber makanan.
                        </p>

                        <p>
                            <span class="font-semibold text-emerald-800">Rantai Makanan</span> menunjukkan hubungan
                            makan dan dimakan dalam ekosistem. Dimulai dari produsen (tumbuhan), konsumen tingkat I
                            (herbivora), konsumen tingkat II (karnivora), hingga pengurai. Contohnya: padi → tikus →
                            ular → elang, kemudian sisa-sisa organisme diuraikan oleh jamur dan bakteri.
                        </p>

                        <p class="text-emerald-800 font-semibold mt-8">
                            Dengan memahami komponen-komponen ekosistem ini, kita bisa lebih menghargai pentingnya
                            menjaga keseimbangan alam dan peran setiap makhluk hidup di dalamnya.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>