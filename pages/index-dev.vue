<template>
  <div>
    <bRow>
      <bCol lg="3">
        <Feature
          :icon="require('../assets/images/feature-icon-01.png')"
          text="Бесплатный Замер"/>
      </bCol>
      <bCol lg="3">
        <Feature
          :icon="require('../assets/images/feature-icon-02.png')"
          text="Пожизненная гарантия"/>
      </bCol>
      <bCol lg="3">
        <Feature
          :icon="require('../assets/images/feature-icon-03.png')"
          text="Опыт более 50 лет"/>
      </bCol>
    </bRow>
    <bRow>
      <bCol md="5">
        <bRow>
          <bCol md="5">
            <Thumbnail
              :url="require('../assets/images/photo-01.png')"
              description="test thumbnail"/>
          </bCol>
          <bCol md="4">
            <Thumbnail
              :url="require('../assets/images/photo-02.png')"
              description="test thumbnail"/>
          </bCol>
        </bRow>
        <bRow>
          <bCol md="4">
            <Thumbnail
              :url="require('../assets/images/photo-03.png')"
              description="test thumbnail"/>
          </bCol>
          <bCol md="5">
            <Thumbnail
              :url="require('../assets/images/photo-04.png')"
              description="test thumbnail"/>
          </bCol>
        </bRow>
      </bCol>
      <bCol
        md="3"
        offset-md="1"
        style="overflow: auto">
        <Article lead-p>
          <h1>наши проекты</h1>
          <h2>для вашего дома</h2>
          <p>
            Мы придумали и разработали крутые столики, необычные светильники, семпатичные стеллажи и многое другое для
            вашего дома.
          </p>
          <p>
            <a href="javascript:void(null);">Посмотреть все</a>
          </p>
        </Article>
      </bCol>
    </bRow>
    <bRow>
      <bCol>
        <Hero
          :illustration="require('../assets/images/hero-illustration.png')"
          :logo="require('../assets/images/logo-hero.png')"
          title="Производство лестниц, дверей, мебели и предметов интерьера из массива дерева">
          Компания Амбер специализируется на производстве столярных изделий из массива дерева ценных пород по
          индивидуальным проектам. Наши клиенты – люди, которые ценят высокое качество, индивидуальность, надежность,
          экологичность, и роскошь натуральных материалов.
        </Hero>
      </bCol>
    </bRow>
  </div>
</template>

<script>
import bRow from 'bootstrap-vue/src/components/layout/row'
import bCol from 'bootstrap-vue/src/components/layout/col'
import Feature from '../components/Feature'
import Article from '../components/Article'
import Thumbnail from '../components/Thumbnail'
import Hero from '../components/Hero'

export default {
  components: {
    bRow,
    bCol,
    Feature,
    Article,
    Thumbnail,
    Hero
  }
}
</script>
