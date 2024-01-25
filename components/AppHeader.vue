<template>
    <header>
        <div id="sticky-header"
            :class="`tg-header__area transparent-header ${isSticky ? 'tg-sticky-menu' : ''} ${isStickyVisible ? 'sticky-menu__show' : ''}`">
            <div class="container custom-container">
                <div class="row">
                    <div class="col-12">
                        <div class="mobile-nav-toggler" @click="handleOpenMobileOffCanvas('/audio/click.wav')">
                            <i class="fas fa-bars"></i>
                        </div>
                        <div class="tgmenu__wrap">
                            <nav class="tgmenu__nav">
                                <div class="logo">
                                    <nuxt-link to="/">
                                        <img src="/images/logo/logo.png" alt="Logo" />
                                    </nuxt-link>
                                </div>
                                <div class="tgmenu__navbar-wrap tgmenu__main-menu d-none d-xl-flex">
                                    <ul class="navigation">
                                        <li class="menu-item-has-children active">
                                            <nuxt-link to="/">
                                                หน้าแรก
                                            </nuxt-link>
                                        </li>
                                        <li class="menu-item-has-children">
                                            <nuxt-link to="#">
                                                หวย
                                            </nuxt-link>
                                        </li>
                                        <li class="menu-item-has-children">
                                            <nuxt-link to="#">
                                                ผลหวย
                                            </nuxt-link>
                                        </li>
                                    </ul>

                                </div>
                                <div class="tgmenu__action d-none d-md-block">
                                    <ul class="list-wrap">
                            
                                        <li class="header-btn">
                                          <nuxt-link to="/login" :class="`${style_2?'tg-btn-3 tg-svg':'tg-border-btn'}`">
                                           <svg-animate-icon v-if="style_2" icon='/images/icons/shape02.svg' id="svg-2" />
                                            <i class="flaticon-edit"></i> ~เข้าสู่ระบบ
                                          </nuxt-link>
                                        </li>
                      
                                      </ul>
                                </div>
                            </nav>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </header>
</template>

<script setup lang="ts">

defineProps<{ style_2?: boolean }>();
const { isSticky, isStickyVisible } = useSticky();
const route = useRoute();
const isActive = ref<boolean>(false);
const isOffCanvasOpen = ref<boolean>(false);
const isMobileOffCanvasOpen = ref<boolean>(false);

const handleOpenSearch = (audioPath: string) => {
    const audio = new Audio(audioPath);
    audio.play();
    isActive.value = !isActive.value;
};

const handleCloseSearch = (audioPath: string) => {
    const audio = new Audio(audioPath);
    audio.play();
    isActive.value = !isActive.value;
};
// off canvas
const handleOpenOffCanvas = (audioPath: string) => {
    const audio = new Audio(audioPath);
    audio.play();
    isOffCanvasOpen.value = !isOffCanvasOpen.value;
};

const handleCloseOffCanvas = (audioPath: string) => {
    const audio = new Audio(audioPath);
    audio.play();
    isOffCanvasOpen.value = !isOffCanvasOpen.value;
};
// mobile off canvas
const handleOpenMobileOffCanvas = (audioPath: string) => {
    const audio = new Audio(audioPath);
    audio.play();
    isMobileOffCanvasOpen.value = !isMobileOffCanvasOpen.value;
};

const handleCloseMobileOffCanvas = (audioPath: string) => {
    const audio = new Audio(audioPath);
    audio.play();
    isMobileOffCanvasOpen.value = !isMobileOffCanvasOpen.value;
};
</script>
