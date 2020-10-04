<template>
  <div class="header">
    <div id="preloader">
      <div class="preload-content">
        <div id="original-load"></div>
      </div>
    </div>

    <!-- Subscribe Modal -->
    <div class="subscribe-newsletter-area">
      <div
        class="modal fade"
        id="subsModal"
        tabindex="-1"
        role="dialog"
        aria-labelledby="subsModal"
        aria-hidden="true"
      >
        <div class="modal-dialog modal-dialog-centered" role="document">
          <div class="modal-content">
            <button
              type="button"
              class="close"
              data-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true">&times;</span>
            </button>
            <div class="modal-body">
              <h5 class="title">Subscribe to my newsletter</h5>
              <form action="#" class="newsletterForm" method="post">
                <input
                  type="email"
                  name="email"
                  id="subscribesForm2"
                  placeholder="Your e-mail here"
                />
                <button type="submit" class="btn original-btn">
                  Subscribe
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>

    <header class="header-area">
      <!-- Top Header Area -->
      <div class="top-header">
        <div class="container h-100">
          <div class="row h-100 align-items-center">
            <!-- Breaking News Area -->
            <div class="col-12 col-sm-8">
              <div class="breaking-news-area">
                <div id="breakingNewsTicker" class="ticker">
                  <ul>
                    <li><a href="#">Hello World!</a></li>
                    <li><a href="#">Hello Universe!</a></li>
                    <li><a href="#">Hello Original!</a></li>
                    <li><a href="#">Hello Earth!</a></li>
                    <li><a href="#">Hello Colorlib!</a></li>
                  </ul>
                </div>
              </div>
            </div>
            <!-- Top Social Area -->
            <div class="col-12 col-sm-4">
              <div class="top-social-area">
                <router-link
                  tag="a"
                  to="/"
                  v-for="(link, index) in links"
                  :key="index"
                  data-toggle="tooltip"
                  data-placement="bottom"
                  :title="link.name"
                >
                  <i :class="link.iconClassName" aria-hidden="true"></i>
                </router-link>
                <!-- <a href="#" data-toggle="tooltip" data-placement="bottom" title="Linkedin"><i class="fa fa-linkedin" aria-hidden="true"></i></a> -->
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Logo Area -->
      <div class="logo-area text-center">
        <div class="container h-100">
          <div class="row h-100 align-items-center">
            <div class="col-12">
              <a href="index.html" class="original-logo"
                ><img src="img/core-img/logo.png" alt=""
              /></a>
            </div>
          </div>
        </div>
      </div>

      <!-- Nav Area -->
      <div class="original-nav-area" id="stickyNav">
        <div class="classy-nav-container breakpoint-off">
          <div class="container">
            <!-- Classy Menu -->
            <nav class="classy-navbar justify-content-between">
              <!-- Subscribe btn -->
              <div class="subscribe-btn">
                <a
                  href="#"
                  class="btn subscribe-btn"
                  data-toggle="modal"
                  data-target="#subsModal"
                  >Subscribe</a
                >
              </div>

              <!-- Navbar Toggler -->
              <div class="classy-navbar-toggler">
                <span class="navbarToggler"
                  ><span></span><span></span><span></span
                ></span>
              </div>

              <!-- Menu -->
              <div class="classy-menu" id="originalNav">
                <!-- close btn -->
                <div class="classycloseIcon">
                  <div class="cross-wrap">
                    <span class="top"></span><span class="bottom"></span>
                  </div>
                </div>

                <!-- Nav Start -->
                <div class="classynav">
                  <ul v-for="(item, index) in items" :key="index">
                    <li>
                      <router-link tag="a" to="/">{{ item.name }}</router-link>
                    </li>
                  </ul>

                  <!-- Search Form  -->
                  <div id="search-wrapper">
                    <form action="#">
                      <input
                        type="text"
                        id="search"
                        placeholder="Search something..."
                      />
                      <div id="close-icon"></div>
                      <input class="d-none" type="submit" value="" />
                    </form>
                  </div>
                </div>
                <!-- Nav End -->
              </div>
            </nav>
          </div>
        </div>
      </div>
    </header>

    <!-- 轮播图 -->
    <div class="hero-area">
      <!-- Hero Slides Area -->
      <div class="hero-slides owl-carousel">
        <!-- Single Slide -->
        <div
          class="single-hero-slide bg-img"
          v-for="(img, index) in images"
          :key="index"
          :style="{ backgroundImage: 'url(' + img.imageUrl + ')' }"
        >
          <div class="container h-100">
            <div class="row h-100 align-items-center">
              <div class="col-12">
                <div class="slide-content text-center">
                  <div class="post-tag">
                    <a href="#" data-animation="fadeInUp">{{
                      img.parent.name
                    }}</a>
                  </div>
                  <h2 data-animation="fadeInUp" data-delay="250ms">
                    <a href="single-post.html">{{ img.title }}</a>
                  </h2>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- 轮播图 -->
    <div class="blog-wrapper section-padding-100 clearfix">
      <div class="container">
        <div class="row align-items-end">
          <!-- Single Blog Area -->
          <div class="col-12 col-lg-4">
            <div class="single-blog-area clearfix mb-100">
              <!-- Blog Content -->
              <div class="single-blog-content">
                <div class="line"></div>
                <a
                  href="#"
                  class="post-tag"
                  v-for="(sort, index) in Lifestyle.sorts"
                  :key="index"
                >
                  {{ sort.name }}
                </a>
                <h4>
                  <a href="#" class="post-headline">{{ Lifestyle.name }}</a>
                </h4>
                <p>{{ Lifestyle.info }}</p>
                <!-- <p v-html="Lifestyle.content"></p> -->
                <a href="#" class="btn original-btn">Read More</a>
              </div>
            </div>
          </div>
          <!-- Single Blog Area -->
          <div class="col-12 col-md-6 col-lg-4">
            <div class="single-catagory-area clearfix mb-100">
              <img :src="Lifestyle.imageUrl" alt="" />
              <!-- Catagory Title -->
              <div
                class="catagory-title"
                v-for="(sort, index) in Lifestyle.sorts"
                :key="index"
              >
                <a href="#">{{ sort.name }}</a>
              </div>
            </div>
          </div>
          <!-- Single Blog Area -->
          <div class="col-12 col-md-6 col-lg-4">
            <div class="single-catagory-area clearfix mb-100">
              <img src="img/blog-img/2.jpg" alt="" />
              <!-- Catagory Title -->
              <div class="catagory-title">
                <a href="#">latest posts</a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- <div class="container">
        <div
          class="single-blog-area blog-style-2 mb-50 wow fadeInUp"
          data-wow-delay="0.4s"
          data-wow-duration="1000ms"
        >
          <div class="row">
            <div class="col-12">
              <div class="single-blog-thumbnail">
                <img src="img/blog-img/7.jpg" alt="" />
                <div class="post-date">
                  <a href="#">10 <span>march</span></a>
                </div>
              </div>
            </div>
            <div class="col-12">
              <div class="single-blog-content mt-50">
                <div class="line"></div>
                <a href="#" class="post-tag">Lifestyle</a>
                <h4>
                  <a href="#" class="post-headline"
                    >10 Tips to organize the perfect party</a
                  >
                </h4>
                <p>
                  Curabitur venenatis efficitur lorem sed tempor. Integer
                  aliquet tempor cursus. Nullam vestibulum convallis risus vel
                  condimentum. Nullam auctor lorem in libero luctus, vel
                  volutpat quam tincidunt.
                </p>
                <div class="post-meta">
                  <p>By <a href="#">james smith</a></p>
                  <p>3 comments</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div> -->

      <div class="container">
         <div class="row">
                <div class="col-12 col-lg-9">
                  <!-- Single Blog Area  -->
                  <div
                    class="single-blog-area blog-style-2 mb-50 wow fadeInUp"
                    data-wow-delay="0.5s"
                    data-wow-duration="1000ms"
                    v-for="(article, index) in february"
                    :key="index"
                  >
                    <div class="row align-items-center">
                      <div class="col-12 col-md-6">
                        <div class="single-blog-thumbnail">
                          <img :src="article.imageUrl" alt="" />
                          <div class="post-date">
                            <a href="#"
                              >12 <span>{{ article.date }}</span></a
                            >
                          </div>
                        </div>
                      </div>

                      <div class="col-12 col-md-6">
                        <!-- Blog Content -->
                        <div class="single-blog-content">
                          <div class="line"></div>
                          <a
                            href="#"
                            class="post-tag"
                            v-for="(sort, index) in article.sorts"
                            :key="index"
                            >{{ sort.name }}</a
                          >
                          <h4>
                            <a href="#" class="post-headline">{{ article.name }}</a>
                          </h4>
                          <p>
                            {{ article.info }}
                          </p>
                          <div class="post-meta">
                            <p>
                              由<a href="#">{{ article.avatar }}</a>
                            </p>
                            <p>3 comments</p>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                  <!-- Single Blog Area  -->
                </div>
                <!-- ##### Sidebar Area ##### -->
                <div class="col-12 col-md-4 col-lg-3">
                    <div class="post-sidebar-area">

                        <!-- Widget Area -->
                        <div class="sidebar-widget-area">
                            <form action="#" class="search-form">
                                <input type="search" name="search" id="searchForm" placeholder="Search">
                                <input type="submit" value="submit">
                            </form>
                        </div>

                        <!-- Widget Area -->
                        <div class="sidebar-widget-area">
                            <h5 class="title subscribe-title">Subscribe to my newsletter</h5>
                            <div class="widget-content">
                                <form action="#" class="newsletterForm">
                                    <input type="email" name="email" id="subscribesForm" placeholder="Your e-mail here">
                                    <button type="submit" class="btn original-btn">Subscribe</button>
                                </form>
                            </div>
                        </div>

                        <!-- Widget Area -->
                        <div class="sidebar-widget-area">
                            <h5 class="title">Advertisement</h5>
                            <a href="#"><img src="img/bg-img/add.gif" alt=""></a>
                        </div>

                        <!-- Widget Area -->
                        <div class="sidebar-widget-area">
                            <h5 class="title">Latest Posts</h5>

                            <div class="widget-content">
                                <!-- Single Blog Post -->
                                <div class="single-blog-post d-flex align-items-center widget-post" v-for="(news,index) in newest" :key="index">
                                    <!-- Post Thumbnail -->
                                    <div class="post-thumbnail">
                                        <img :src="news.imageUrl" alt="">
                                    </div>
                                    <!-- Post Content -->
                                    <div class="post-content">
                                        <a href="#" class="post-tag" v-for="(sort,index) in news.sorts" :key="index">{{sort.name}}</a>
                                        <h4><a href="#" class="post-headline">{{news.name}}</a></h4>
                                        <div class="post-meta">
                                            <p><a href="#">{{news.date}}</a></p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Widget Area -->
                        <div class="sidebar-widget-area">
                            <h5 class="title">Tags</h5>
                            <div class="widget-content">
                                <ul class="tags">
                                    <router-link to="/" tag="li" v-for="(tag,index) in tags" :key="index">
                                        <a href="#">{{tag.name}}</a>
                                    </router-link>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default {
  name: "home",
  data() {
    return {
      items: [],
      links: [],
      images: [],
      articles: [],
      Lifestyle: [],
      february: [],
      tags:[],
      newest:[],
    };
  },

  methods: {
    // 首页导航数据
    async feach() {
      const res = await this.$http.get("/categories/all");
      res.data.forEach((item, index) => {
        if (item.parent == undefined) {
          this.items.push(item);
        }
      });
    },

    // 获取tags数据
    async tagsload(){
      const res = await this.$http.get("/categories/tags");
      this.tags = res.data.children;
    },

    // 获取最新帖子数据
    async newestload(){
      const res = await this.$http.get('/article/newdate');
      this.newest = res.data;
    },

    // 首页友链数据
    async linkload() {
      const res = await this.$http.get("/links/list");
      this.links = res.data;
    },

    // 轮播图数据
    async imageload() {
      const res = await this.$http.get("/images/list");
      this.images = res.data;
    },

    // 文章数据
    async articleload() {
      const res = await this.$http.get("/article/init");
      this.articles = res.data;
    },

    // 获取生活方式数据
    async articleLifestyle() {
      const res = await this.$http.get("/article/lifestyle");
      this.Lifestyle = res.data;
    },

    // 获取二月份数据
    async articleFebruary() {
      const res = await this.$http.get("/article/ctimelist");
      this.february = res.data;
    },
  },

  created() {
    this.feach();
    this.linkload();
    this.tagsload();
    this.newestload();
    this.imageload();
    this.articleload();
    this.articleLifestyle();
    this.articleFebruary();
  },
};
</script>