// 7Œ3 CAMBIO 1: Subimos la versiš®n a v2 para obligar a actualizar el HTML nuevo
const CACHE_NAME = 'pos-ayala-v2';

// Archivos que queremos que funcionen sin internet
const urlsToCache = [
  './',
  './index.html', // Tu Login
  './app.html',   // 7Œ3 IMPORTANTE: Tu App principal (agršŠgala aqušª)
  './manifest.json',
  './logo.png'    // Es bueno cachear el logo tambišŠn
];

// Instalaciš®n del Service Worker
self.addEventListener('install', event => {
  // Obliga al SW a activarse inmediatamente sin esperar
  self.skipWaiting(); 
  
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then(cache => {
        console.log('Abriendo cachšŠ v2');
        return cache.addAll(urlsToCache);
      })
  );
});

// Activar y limpiar cachšŠs viejas (v1)
self.addEventListener('activate', event => {
  event.waitUntil(
    caches.keys().then(cacheNames => {
      return Promise.all(
        cacheNames.map(cacheName => {
          if (cacheName !== CACHE_NAME) {
            console.log('Borrando cachšŠ antigua:', cacheName);
            return caches.delete(cacheName);
          }
        })
      );
    })
  );
});

// Responder cuando no hay internet
self.addEventListener('fetch', event => {
  event.respondWith(
    caches.match(event.request)
      .then(response => response || fetch(event.request))
  );
});
