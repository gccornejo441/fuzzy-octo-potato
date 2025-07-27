<script lang="ts">
  export let level: 'UNCLASSIFIED' | 'CUI' | 'CONFIDENTIAL' | 'SECRET' | 'TOP SECRET' = 'CUI';

  const bannerColors: Record<string, string> = {
    'UNCLASSIFIED': 'bg-green-700 text-white',
    'CUI': 'bg-purple-800 text-white',
    'CONFIDENTIAL': 'bg-blue-700 text-white',
    'SECRET': 'bg-red-600 text-white',
    'TOP SECRET': 'bg-orange-600 text-black',
  };

  const bannerText = level.toUpperCase();
</script>

<style>
.cui-banner {
  position: fixed;
  left: 0;
  right: 0;
  z-index: 1000;
  text-align: center;
  font-weight: bold;
  font-size: 1rem;
  letter-spacing: 0.1em;
  height: 1.5rem;         
  line-height: 1.5rem;   
  padding: 0;              
}

.cui-banner-top {
  top: 0;
}

.cui-banner-bottom {
  bottom: 0;
}

.cui-banner-spacer {
  height: 1.5rem;            
}
</style>

<!-- TOP Banner -->
<div class="cui-banner cui-banner-top {bannerColors[level]}">
  {bannerText}
</div>
<div class="cui-banner-spacer"></div>

<slot />

<!-- BOTTOM Banner -->
<!-- <div class="cui-banner cui-banner-bottom {bannerColors[level]}">
  {bannerText}
</div> -->
