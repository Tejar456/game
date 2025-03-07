<template>
    <div class="h-screen relative overflow-y-auto">
        <img src="assets/img/6.jpg" alt="Background" class="w-full h-full object-cover fixed inset-0">

        <div class="relative min-h-screen flex items-center justify-center py-6 px-4">
            <div
                class="border-2 border-green-900 p-4 sm:p-6 md:p-8 rounded-xl bg-gradient-to-br bg-white backdrop-blur-sm shadow-xl w-full max-w-[800px] mx-auto">
                <h1 class="text-xl sm:text-2xl md:text-3xl font-sans font-bold text-green-700 text-center mb-4 sm:mb-6">
                    Tentang Game
                </h1>
                <div class="space-y-4 sm:space-y-6 text-white">
                    <div class="bg-green-600/85 p-4 sm:p-6 rounded-lg">
                        <h2 class="font-sans text-lg sm:text-xl mb-3 sm:mb-4">Tim Pengembang: Green Warriors</h2>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 sm:gap-4 mb-4 sm:mb-6">
                            <div class="bg-green-700/30 p-3 rounded-lg">
                                <div class="flex items-center space-x-2">
                                    <div class="w-2 h-2 bg-green-200 rounded-full"></div>
                                    <span class="font-medium text-sm sm:text-base">Tejar Maulana</span>
                                </div>
                            </div>
                            <div class="bg-green-700/30 p-3 rounded-lg">
                                <div class="flex items-center space-x-2">
                                    <div class="w-2 h-2 bg-green-200 rounded-full"></div>
                                    <span class="font-medium text-sm sm:text-base">Dita Nur Sabila</span>
                                </div>
                            </div>
                            <div class="bg-green-700/30 p-3 rounded-lg">
                                <div class="flex items-center space-x-2">
                                    <div class="w-2 h-2 bg-green-200 rounded-full"></div>
                                    <span class="font-medium text-sm sm:text-base">Melva Azkyadina</span>
                                </div>
                            </div>
                            <div class="bg-green-700/30 p-3 rounded-lg">
                                <div class="flex items-center space-x-2">
                                    <div class="w-2 h-2 bg-green-200 rounded-full"></div>
                                    <span class="font-medium text-sm sm:text-base">Salma Tsaniatul</span>
                                </div>
                            </div>
                        </div>
                        <p class="text-sm sm:text-base leading-relaxed">
                            Game ini dirancang untuk mengedukasi para pemain tentang komponen ekosistem lingkungan
                            melalui quiz dalam game ini.
                        </p>
                    </div>
                </div>

                <h1 class="text-xl sm:text-2xl md:text-3xl font-sans font-bold text-green-700 text-center mt-6 mb-4">
                    Peraturan Game
                </h1>
                <div class="space-y-4 text-white">
                    <div class="bg-green-600/85 p-4 rounded-lg">
                        <h2 class="font-semibold text-lg sm:text-xl mb-2">Cara Bermain:</h2>
                        <ul class="list-disc list-inside space-y-2 text-sm sm:text-base">
                            <li>Pilih jawaban yang benar dari pilihan yang tersedia</li>
                            <li>Tidak bisa kembali ke pertanyaan sebelumnya</li>
                            <li>Skor akan dihitung berdasarkan jawaban benar</li>
                        </ul>
                    </div>

                    <div class="mt-6 sm:mt-8 flex justify-center">
                        <NuxtLink to="/" class="px-4 sm:px-6 py-2 sm:py-3 bg-transparent border-green-700 border text-green-700 text-lg md:text-xl 
                font-semibold font-sans rounded-full hover:bg-green-200 transform hover:scale-105 transition-all duration-300 
                shadow-lg hover:shadow-xl">
                            Kembali ke Menu
                        </NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>