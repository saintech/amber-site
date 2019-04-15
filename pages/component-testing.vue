<template>
  <div>
    <bRow>
      <bCol>
        <p>
          <Button>Regular Button</Button>
          <Button type="primary">Primary</Button>
        </p>
        <p style="line-height: 2.5rem;">
          <Button type="success">Success</Button>
          <Button type="warning">Warning</Button>
          <Button type="danger">Danger</Button>
        </p>
        <p>
          <Button size="large">Large</Button>
          <Button size="small">Small</Button>
        </p>
        <bRow>
          <bCol lg="7">
            <Feature
              text="Feature test"
              icon="https://via.placeholder.com/90x90?text=icon"/>
          </bCol>
        </bRow>
        <bRow>
          <bCol>
            <Feature
              text="Feature test"
              icon="https://via.placeholder.com/90x90?text=icon"/>
          </bCol>
        </bRow>
      </bCol>
      <bCol
        md="4"
        style="overflow: auto">
        <Article lead-p>
          <h1>Heading</h1>
          <h2>Heading 2</h2>
          <h3>Heading 3</h3>
          <h4>Heading 4</h4>
          <h5>Heading 5</h5>
          <h6>Heading 6</h6>
          <p>
            Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.
          </p>
          <p>
            Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient
            montes, nascetur ridiculus mus. Nullam id dolor id nibh ultricies vehicula.
          </p>
          <p>
            <a href="javascript:void(null);">test link</a>
          </p>
        </Article>
      </bCol>
    </bRow>
    <bRow>
      <bCol
        xl="3"
        lg="4"
        md="4">
        <Product icon="https://via.placeholder.com/240x200?text=product">
          <p>
            Cras justo odio
          </p>
          <p>
            Some quick example text to build on the card title.
          </p>
        </Product>
      </bCol>
      <bCol
        xl="4"
        lg="5"
        md="5">
        <Product icon="https://via.placeholder.com/240x200?text=product">
          <p>
            Cras justo odio
          </p>
          <p>
            Some quick example text to build on the card title and make up the bulk of the card's content.
            Nullam quis risus eget urna mollis ornare vel eu leo.
          </p>
        </Product>
      </bCol>
      <bCol
        xl="2"
        lg="3"
        md="3">
        <Product icon="https://via.placeholder.com/240x200?text=product">
          <p>
            Cras justo odio
          </p>
          <p>
            Some quick example text to build on the card title and make up the bulk of the card's content.
          </p>
        </Product>
      </bCol>
    </bRow>
    <bRow>
      <bCol>
        <Hero
          logo="https://via.placeholder.com/1000x200?text=logo"
          illustration="https://via.placeholder.com/650x325?text=illustration"
          title="Hero header">
          Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient
          montes, nascetur ridiculus mus. Nullam id dolor id nibh ultricies vehicula.
        </Hero>
      </bCol>
    </bRow>
    <bRow>
      <bCol
        lg="3"
        md="3">
        <Thumbnail
          url="https://via.placeholder.com/600x500"
          description="test thumbnail"/>
      </bCol>
      <bCol
        lg="5"
        md="6">
        <Thumbnail
          url="https://via.placeholder.com/600x500"
          description="test thumbnail"/>
      </bCol>
      <bCol
        lg="1"
        md="2"
        sm="3"
        cols="6">
        <Thumbnail
          url="https://via.placeholder.com/600x500"
          description="test thumbnail"/>
      </bCol>
    </bRow>
    <bRow>
      <bCol style="position: inherit">
        <Gallery
          :images="
            [{ url: 'https://via.placeholder.com/600x500', description: 'test image' },
             { url: 'https://via.placeholder.com/500x500', description: 'test image' },
             { url: 'https://via.placeholder.com/200x500', description: 'test image' },
             { url: 'https://via.placeholder.com/600x500', description: 'test image' },
             { url: 'https://via.placeholder.com/200x500', description: 'test image' },
             { url: 'https://via.placeholder.com/600x500', description: 'test image' },
             { url: 'https://via.placeholder.com/600x500', description: 'test image' }]"/>
      </bCol>
    </bRow>
  </div>
</template>

<script>
import bRow from 'bootstrap-vue/src/components/layout/row'
import bCol from 'bootstrap-vue/src/components/layout/col'
import Button from '../components/Button'
import Article from '../components/Article'
import Feature from '../components/Feature'
import Product from '../components/Product'
import Hero from '../components/Hero'
import Thumbnail from '../components/Thumbnail'
import Gallery from '../components/Gallery'

export default {
  components: {
    Gallery,
    Thumbnail,
    Hero,
    Product,
    Feature,
    Article,
    Button,
    bRow,
    bCol
  }
}
</script>
