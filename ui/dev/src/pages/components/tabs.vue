<template>
  <div class="tabs-demo q-py-xl">
    <div class="">
      <div>
        <q-checkbox v-model="dense" label="Dense" />
      </div>

      <div style="display: flex; margin-bottom: 50px; height: 200px; position: relative;">
        <q-tabs :dense="dense" vertical class="vertical-tabs" v-model="vtab" style="margin-right: 25px;">
          <q-tab name="one" icon="wifi" />
          <q-tab name="two" icon="bluetooth" />
          <q-tab name="three" icon="map" />
        </q-tabs>

        <q-tabs :dense="dense" vertical inline-label class="vertical-tabs" v-model="vtab" style="margin-right: 25px;">
          <q-tab :ripple="{ early: true }" name="one" label="wifi" icon="wifi" />
          <q-tab :ripple="{ early: true }" name="two" label="bluetooth" icon="bluetooth" />
          <q-tab :ripple="{ early: true }" name="three" label="map" icon="map" />
          <q-tab :ripple="{ early: true }" name="four" label="phone" icon="phone" />
          <q-tab :ripple="{ early: true }" name="five" label="location" icon="location_on" />
          <q-tab :ripple="{ early: true }" name="six" label="favorite" icon="favorite" />
          <q-tab :ripple="{ early: true }" name="seven" label="home" icon="home" />
          <q-tab :ripple="{ early: true }" name="eight" label="info" icon="info" />
        </q-tabs>

        <q-tabs :dense="dense" vertical class="vertical-tabs" v-model="vtab" style="margin-right: 25px;">
          <q-tab name="one" label="wifi" icon="wifi" />
          <q-tab name="two" label="bluetooth" icon="bluetooth" />
          <q-tab name="three" label="map" icon="map" />
          <q-tab name="four" label="phone" icon="phone" />
          <q-tab name="five" label="location" icon="location_on" />
          <q-tab name="six" label="favorite" icon="favorite" />
          <q-tab name="seven" label="home" icon="home" />
          <q-tab name="eight" label="info" icon="info" />
        </q-tabs>
      </div>

      <q-tabs :dense="dense">
        <q-tab label="Item one - tooltip">
          <q-tooltip>
            <q-icon name="wifi" /> Wifi
          </q-tooltip>
        </q-tab>
        <q-tab label="Item two - menu">
          <q-menu transition-show="jump-down">
            <input v-model="gigi">
            <q-list padding style="min-width: 100px">
              <q-item
                v-for="n in 20"
                :key="n"
                clickable
                v-close-popup
              >
                <q-item-section>Label</q-item-section>
              </q-item>
            </q-list>
          </q-menu>
        </q-tab>
        <q-tab label="Item three" />
        <q-btn-dropdown stretch flat label="Dropdown">
          <q-list link>
            <q-item-label header>
              Folders
            </q-item-label>
            <q-item v-for="n in 3" :key="`x.${n}`" clickable v-close-popup tabindex="0">
              <q-item-section avatar>
                <q-avatar icon="folder" color="secondary" text-color="white" />
              </q-item-section>
              <q-item-section>
                <q-item-label>Photos</q-item-label>
                <q-item-label caption>
                  February 22, 2016
                </q-item-label>
              </q-item-section>
              <q-item-section side>
                <q-icon name="info" />
              </q-item-section>
            </q-item>
            <q-separator inset />
            <q-item-label header>
              Files
            </q-item-label>
            <q-item v-for="n in 3" :key="`y.${n}`" clickable v-close-popup tabindex="0">
              <q-item-section avatar>
                <q-avatar icon="assignment" color="primary" text-color="white" />
              </q-item-section>
              <q-item-section>
                <q-item-label>Vacation</q-item-label>
                <q-item-label caption>
                  February 22, 2016
                </q-item-label>
              </q-item-section>
              <q-item-section side>
                <q-icon name="info" />
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-tabs>

      <q-tabs :dense="dense" :breakpoint="1000" align="right">
        <q-tab icon="phone" />
        <q-tab icon="favorite" />
        <q-tab icon="location_on" />
      </q-tabs>

      <q-tabs :dense="dense" inline-label active-class="dev-tabs-active-class">
        <q-tab icon="map">
          <q-badge color="red" floating>
            2
          </q-badge>
        </q-tab>
        <q-tab label="Map" alert="red" alert-icon="map" />
        <q-tab icon="map" label="Map">
          <q-badge color="red" floating>
            2
          </q-badge>
        </q-tab>
        <q-tab icon="map" alert />
        <q-tab icon="map" label="Map" alert />
        <q-tab icon="location_on" />
      </q-tabs>

      <q-tabs :dense="dense" class="bg-grey-1 text-teal">
        <q-tab icon="phone" label="Item one Item one Item one" />
        <q-tab icon="favorite" label="Item two" />
        <q-tab icon="location_on" label="Item three" />
      </q-tabs>

      <q-toolbar class="bg-purple text-white shadow-2 rounded-borders q-mb-xl">
        <q-btn flat label="Homepage" />
        <q-space />
        <q-tabs inline-label class="col-shrink">
          <q-tab icon="phone" label="Tab 1" />
          <q-tab label="Tab 2" />
          <q-tab icon="location_on" label="Tab 3" />
        </q-tabs>
      </q-toolbar>

      <q-tabs :dense="dense" class="bg-grey-1 text-teal">
        <q-tab icon="phone" label="Item one Item one Item one" />
        <q-tab label="Item two" />
        <q-tab icon="location_on" label="Item three" />
      </q-tabs>

      <q-tabs :dense="dense" narrow-indicator>
        <q-tab icon="phone" label="Item one Item one Item one" />
        <q-tab icon="favorite" label="Item two" />
        <q-tab icon="location_on" label="Item three" />
      </q-tabs>

      <q-tabs :dense="dense" inline-label class="bg-purple text-white">
        <q-tab icon="phone" label="Item one Item one Item one" />
        <q-tab icon="favorite" label="Item two" />
        <q-tab icon="location_on" label="Item three" />
        <q-btn-dropdown stretch flat label="Dropdown">
          <q-list link>
            <q-item-label header>
              Folders
            </q-item-label>
            <q-item v-for="n in 3" :key="`x.${n}`" clickable v-close-popup tabindex="0">
              <q-item-section avatar>
                <q-avatar icon="folder" color="secondary" text-color="white" />
              </q-item-section>
              <q-item-section>
                <q-item-label>Photos</q-item-label>
                <q-item-label caption>
                  February 22, 2016
                </q-item-label>
              </q-item-section>
              <q-item-section side>
                <q-icon name="info" />
              </q-item-section>
            </q-item>
            <q-separator inset />
            <q-item-label header>
              Files
            </q-item-label>
            <q-item v-for="n in 3" :key="`y.${n}`" clickable v-close-popup tabindex="0">
              <q-item-section avatar>
                <q-avatar icon="assignment" color="primary" text-color="white" />
              </q-item-section>
              <q-item-section>
                <q-item-label>Vacation</q-item-label>
                <q-item-label caption>
                  February 22, 2016
                </q-item-label>
              </q-item-section>
              <q-item-section side>
                <q-icon name="info" />
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-tabs>

      <q-tabs :dense="dense" class="bg-teal text-yellow" switch-indicator inline-label>
        <q-tab icon="phone" label="Item one" />
        <q-tab icon="favorite" label="-- Switch indicator --" />
        <q-tab icon="location_on" label="Item three" />
      </q-tabs>

      <q-tabs :dense="dense" class="bg-white" inline-label active-bg-color="purple" active-color="white" indicator-color="transparent">
        <q-tab icon="phone" label="Item one" />
        <q-tab icon="favorite" label="Item two" />
        <q-tab icon="location_on" label="Item three" />
      </q-tabs>

      <q-tabs :dense="dense" inline-label align="justify" indicator-color="orange">
        <q-tab icon="phone" label="Item one" />
        <q-tab icon="favorite" label="Item two" />
        <q-tab icon="location_on" label="Item three" />
        <q-tab icon="phone" label="Item four" />
        <q-tab icon="favorite" label="Item five" />
        <q-tab icon="location_on" label="Item six" />
      </q-tabs>

      <div class="row q-col-gutter-xs justify-stretch">
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace to="/components/tabs/a#123" active-class="r-link--active" exact-active-class="r-link--exact-active">
            /tabs/a#123 - select most specific tab
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace to="/components/tabs/a/a#1" active-class="r-link--active" exact-active-class="r-link--exact-active">
            /tabs/a/a#1 - select exact tab
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace to="/components/tabs/a/a#123" active-class="r-link--active" exact-active-class="r-link--exact-active">
            /tabs/a/a#123 - select most specific tab
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace to="/components/tabs/a/a" active-class="r-link--active" exact-active-class="r-link--exact-active">
            /tabs/a/a - select exact tab
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace to="/components/tabs/b#123" active-class="r-link--active" exact-active-class="r-link--exact-active">
            /tabs/b#123 - select most specific tab
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace to="/components/tabs/c" active-class="r-link--active" exact-active-class="r-link--exact-active">
            /tabs/c - select nothing
          </router-link>
        </div>
      </div>
      <q-tabs :dense="dense" class="test q-mt-sm">
        <q-route-tab name="tabs" replace to="/components/tabs" exact label="/tabs" no-caps />
        <!-- <q-route-tab name="tabs/a" replace to="/components/tabs/a" exact label="/tabs/a" no-caps /> -->
        <q-route-tab name="tabs/a*" replace to="/components/tabs/a" label="/tabs/a[...]" no-caps />
        <q-route-tab name="tabs/a#1" replace to="/components/tabs/a#1" exact label="/tabs/a#1" no-caps />
        <q-route-tab name="tabs/a/a" replace to="/components/tabs/a/a" exact label="/tabs/a/a" no-caps />
        <q-route-tab name="tabs/a/a*" replace to="/components/tabs/a/a" label="/tabs/a/a[...]" no-caps />
        <q-route-tab name="tabs/a/a#1" replace to="/components/tabs/a/a#1" exact label="/tabs/a/a#1" no-caps />
        <q-route-tab name="tabs/a/b" replace to="/components/tabs/a/b" exact label="/tabs/a/b" no-caps />
        <q-route-tab name="tabs/b" replace to="/components/tabs/b" exact label="/tabs/b" no-caps />
        <q-route-tab name="tabs/b/a" replace to="/components/tabs/b/a" exact label="/tabs/b/a" no-caps />
      </q-tabs>

      <div class="row q-col-gutter-xs justify-stretch">
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace :to="{ name: 'ta', params: { id: 1 }}" active-class="r-link--active" exact-active-class="r-link--exact-active">
            t/1/a
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace :to="{ name: 'tb', params: { id: 1 }}" active-class="r-link--active" exact-active-class="r-link--exact-active">
            t/1/b
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace :to="{ name: 'ta', params: { id: 2 }}" active-class="r-link--active" exact-active-class="r-link--exact-active">
            t/2/a
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" replace :to="{ name: 'tb', params: { id: 2 }}" active-class="r-link--active" exact-active-class="r-link--exact-active">
            t/2/b
          </router-link>
        </div>
      </div>
      <q-tabs :dense="dense" class="test q-mt-sm">
        <q-route-tab to="/components/tabs/t" exact label="t" />
        <q-route-tab v-if="$route.params.id" :to="{ name: 'ta', params: $route.params }" exact :label="`t/${ $route.params.id }/a`" />
        <q-route-tab v-if="$route.params.id" :to="{ name: 'tb', params: $route.params }" exact :label="`t/${ $route.params.id }/b`" />
      </q-tabs>

      <div class="row q-col-gutter-xs justify-stretch">
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r => r.1
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r?q=2" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r q=2 => r.1 q=2
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/1?a=1" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.1 a=1
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/1/1" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.1.1
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/1?q=1" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.1 q=1
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/1/1?a=1" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.1.1 a=1
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/1/2" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.1.2 => r => r.1
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/1/3" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.1.3 => r.1.1
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/2" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.2
          </router-link>
        </div>
        <div class="col-12 col-sm-4 col-md">
          <router-link class="r-link" to="/components/tabs/r/3" replace active-class="r-link--active" exact-active-class="r-link--exact-active">
            r.3
          </router-link>
        </div>
      </div>
      <q-toggle v-model="exact" label="Show exact match tabs" />
      <q-toggle v-model="loose" label="Show loose match tabs" />
      <q-tabs :dense="dense" class="test q-mt-sm">
        <q-route-tab v-if="exact" key="01" :to="{ name: 'r' }" exact label="r" />
        <q-route-tab v-if="loose" key="02" :to="{ name: 'r' }" label="r *" />
        <q-route-tab v-if="exact" key="03" :to="{ name: 'r.1', query: { q: '1' } }" exact label="r.1 q=1" />
        <q-route-tab v-if="loose" key="04" :to="{ name: 'r.1', query: { q: '1' } }" label="r.1 q=1 *" />
        <q-route-tab v-if="loose" key="15" :to="{ name: 'r.1', query: { q: '1' } }" label="r.1 q=1 * disabled" disable />
        <q-route-tab v-if="exact" key="05" :to="{ name: 'r.1.1' }" exact label="r.1.1" />
        <q-route-tab v-if="loose" key="06" :to="{ name: 'r.1.1' }" label="r.1.1 *" />
        <q-route-tab v-if="exact" key="07" :to="{ name: 'r.1.2' }" exact label="r.1.2" />
        <q-route-tab v-if="loose" key="08" :to="{ name: 'r.1.2' }" label="r.1.2 *" />
        <q-route-tab v-if="exact" key="09" :to="{ name: 'r.1.3' }" exact label="r.1.3" />
        <q-route-tab v-if="loose" key="10" :to="{ name: 'r.1.3' }" label="r.1.3 *" />
        <q-route-tab v-if="exact" key="11" :to="{ name: 'r.2' }" exact label="r.2" />
        <q-route-tab v-if="loose" key="12" :to="{ name: 'r.2' }" label="r.2 *" />
        <q-route-tab v-if="exact" key="13" :to="{ name: 'r.3' }" exact label="r.3" />
        <q-route-tab v-if="loose" key="14" :to="{ name: 'r.3' }" label="r.3 *" />
      </q-tabs>

      <div class="q-text-subtitle2">Custom click action</div>
      <q-tabs :dense="dense" class="test q-mt-sm">
        <q-route-tab key="1" :to="{ name: 'r.1' }" label="r.1 - delay 2sec" @click="routeNavDelay" />
        <q-route-tab key="2" :to="{ name: 'r.1.1' }" label="r.1.1 disabled - delay 2sec" disable @click="routeNavDelay" />
        <q-route-tab key="3" :to="{ name: 'r.2' }" label="r.2 - passthrough" @click="routeNavPass" />
        <q-route-tab key="4" :to="{ name: 'r.2' }" label="r.2 - delay 2sec" @click="routeNavDelay" />
        <q-route-tab key="5" :to="{ name: 'r.2' }" label="r.2 - cancel" @click="routeNavCancel" />
        <q-route-tab key="6" :to="{ name: 'r.3' }" label="r.3 - redirect to r.1.1" @click="routeNavChange" />
      </q-tabs>

      <h4>Tabs model (respect model): {{ tabModel }}</h4>
      <q-tabs :dense="dense" :model-value="tabModel" @update:model-value="onChangeTab1" class="bg-grey-1 text-teal">
        <q-tab name="one" label="One" />
        <q-tab name="two" label="Two -> One" />
        <q-tab name="three" label="Three (no way)" />
        <q-tab name="four" label="Four" />
        <q-tab name="five" label="Five" />
      </q-tabs>
      <q-tabs :dense="dense" :model-value="tabModel" @update:model-value="onChangeTab2" class="bg-grey-1 text-teal">
        <q-tab name="one" label="One -> Two" />
        <q-tab name="two" label="Two" />
        <q-tab name="three" label="Three" />
        <q-tab name="four" label="Four (no way)" />
        <q-tab name="five" label="Five" />
      </q-tabs>
      <q-tabs :dense="dense" v-model="tabModel" class="bg-grey-1 text-teal">
        <q-tab name="one" label="One" />
        <q-tab name="two" label="Two" />
        <q-tab name="three" label="Three" />
        <q-tab name="four" label="Four" />
        <q-tab name="five" label="Five" />
      </q-tabs>

      <h4>Tabs content (animated, swipeable)</h4>
      <q-option-group
        type="radio"
        v-model="tab"
        :options="[
          {label: 'One', value: 'one'},
          {label: 'Two', value: 'two'},
          {label: 'Three', value: 'three'},
          {label: 'Bogus', value: 'bogus'}
        ]"
        inline
        class="q-ma-md"
      />
      <q-toggle v-model="panelTest" label="Panel test; Swap one with two / Remove tab two" />

      <div class="shadow-1 q-ma-md">
        <q-tabs
          :dense="dense"
          v-model="tab"
          active-color="white"
          indicator-color="yellow"
          class="bg-cyan text-white"
          style="margin-bottom: 0"
        >
          <q-tab name="one" icon="phone" label="One" />
          <q-tab name="two" icon="favorite" label="Two" />
          <q-tab name="three" icon="location_on" label="Three" />
          <q-tab disable name="four" icon="map" label="Four" />
        </q-tabs>

        <q-tab-panels
          v-model="tab"
          swipeable
          animated
          infinite
          keep-alive
          class="text-center"
        >
          <q-tab-panel :name="panelTest ? 'two' : 'one'">
            <q-btn dense round icon="map" class="absolute-bottom-right" />
            Tab One <strong v-if="panelTest">(Swapped)</strong> <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident obcaecati repellendus dolores totam nostrum ut repudiandae perspiciatis est accusamus, eaque natus modi rem beatae optio cumque, velit ducimus autem magnam.
            <keep-alive-test name="one" />
          </q-tab-panel>

          <q-tab-panel :name="panelTest ? 'one' : 'two'">
            Tab Two <strong v-if="panelTest">(Swapped)</strong>  <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. At iusto neque odio porro, animi ducimus iure autem commodi sint, magni voluptatum molestias illo accusamus voluptate ratione aperiam. Saepe, fugiat vel.
            <keep-alive-test name="two" />
          </q-tab-panel>

          <q-tab-panel name="three">
            Tab Three <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis labore inventore accusantium, perferendis eos sapiente culpa consectetur deserunt praesentium cumque distinctio placeat, recusandae id qui odit similique officia? Mollitia, ea!
            <keep-alive-test name="three" />
          </q-tab-panel>

          <q-tab-panel disable name="four">
            Tab Four <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis labore inventore accusantium, perferendis eos sapiente culpa consectetur deserunt praesentium cumque distinctio placeat, recusandae id qui odit similique officia? Mollitia, ea!
            <keep-alive-test name="four" />
          </q-tab-panel>
        </q-tab-panels>
      </div>

      <q-tab-panels
        v-model="tab"
        swipeable
        animated
        transition-prev="scale"
        transition-next="scale"
        class="text-center"
      >
        <q-tab-panel name="one">
          <q-btn dense round icon="map" class="absolute-bottom-right" />
          v-if test Tab One <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident obcaecati repellendus dolores totam nostrum ut repudiandae perspiciatis est accusamus, eaque natus modi rem beatae optio cumque, velit ducimus autem magnam.
        </q-tab-panel>

        <q-tab-panel v-if="!panelTest" name="two">
          v-if test Tab Two <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. At iusto neque odio porro, animi ducimus iure autem commodi sint, magni voluptatum molestias illo accusamus voluptate ratione aperiam. Saepe, fugiat vel.
        </q-tab-panel>

        <q-tab-panel name="three">
          v-if test Tab Three <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis labore inventore accusantium, perferendis eos sapiente culpa consectetur deserunt praesentium cumque distinctio placeat, recusandae id qui odit similique officia? Mollitia, ea!
        </q-tab-panel>

        <q-tab-panel disable name="four">
          v-if test Tab Four <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis labore inventore accusantium, perferendis eos sapiente culpa consectetur deserunt praesentium cumque distinctio placeat, recusandae id qui odit similique officia? Mollitia, ea!
        </q-tab-panel>
      </q-tab-panels>

      <q-tab-panels
        v-model="tab"
        swipeable
        animated
        transition-prev="fade"
        transition-next="fade"
        class="q-mt-lg text-center"
        style="height: 150px"
      >
        <q-tab-panel name="one">
          Tab One <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident obcaecati repellendus dolores totam nostrum ut repudiandae perspiciatis est accusamus, eaque natus modi rem beatae optio cumque, velit ducimus autem magnam.
          <q-input v-model="text" />
          <input v-model="text">
          <q-btn dense round icon="map" class="absolute-bottom-right" />
          Tab One <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident obcaecati repellendus dolores totam nostrum ut repudiandae perspiciatis est accusamus, eaque natus modi rem beatae optio cumque, velit ducimus autem magnam.
        </q-tab-panel>

        <q-tab-panel name="two">
          Tab Two <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident obcaecati repellendus dolores totam nostrum ut repudiandae perspiciatis est accusamus, eaque natus modi rem beatae optio cumque, velit ducimus autem magnam.
          <q-input v-model="text" />
          <input v-model="text">
          <q-btn dense round icon="map" class="absolute-bottom-right" />
          Tab Two <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident obcaecati repellendus dolores totam nostrum ut repudiandae perspiciatis est accusamus, eaque natus modi rem beatae optio cumque, velit ducimus autem magnam.
        </q-tab-panel>

        <q-tab-panel name="three">
          Tab Three <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis labore inventore accusantium, perferendis eos sapiente culpa consectetur deserunt praesentium cumque distinctio placeat, recusandae id qui odit similique officia? Mollitia, ea!
        </q-tab-panel>

        <q-tab-panel disable name="four">
          Tab Four <br> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis labore inventore accusantium, perferendis eos sapiente culpa consectetur deserunt praesentium cumque distinctio placeat, recusandae id qui odit similique officia? Mollitia, ea!
        </q-tab-panel>
      </q-tab-panels>
    </div>
  </div>
</template>

<script>
import { h, ref, onBeforeMount, onMounted, onBeforeUnmount, onActivated, onDeactivated } from 'vue'
import { uid } from 'quasar'

export default {
  components: {
    KeepAliveTest: {
      name: 'KeepAliveTest',

      props: {
        name: String
      },

      setup (props) {
        const counter = ref(0)
        const id = uid()

        function log (what) {
          console.log(`[KeepAliveTest > ${ props.name } / ${ id }] ${ what }`)
        }

        log('created')

        onBeforeMount(() => {
          log('onBeforeMount')
        })

        onMounted(() => {
          log('onMounted')
        })

        onBeforeUnmount(() => {
          log('onBeforeUnmount')
        })

        onActivated(() => {
          log('onActivated')
        })

        onDeactivated(() => {
          log('onDeactivated')
        })

        function onClick () {
          counter.value += 1
        }

        return () => h('div', {
          class: 'q-pa-sm bg-grey-2 cursor-pointer',
          onClick
        }, `${ props.name } - clicked ${ counter.value } times [${ id }]`)
      }
    }
  },

  data () {
    return {
      text: '',
      gigi: '',
      dense: false,
      tab: 'one',
      tabModel: null,
      vtab: 'one',
      panelTest: false,
      some: false,
      exact: true,
      loose: true
    }
  },

  methods: {
    onChangeTab1 (val) {
      if (val === 'two') {
        this.tabModel = 'one'
      }
      else if (val !== 'three') {
        this.tabModel = val
      }
    },

    onChangeTab2 (val) {
      if (val === 'one') {
        this.tabModel = 'two'
      }
      else if (val !== 'four') {
        this.tabModel = val
      }
    },

    routeNavDelay (e, go) {
      e.preventDefault()
      setTimeout(go, 2000)
    },

    routeNavPass () {},

    routeNavCancel (e) {
      e.preventDefault()
    },

    routeNavChange (e, go) {
      e.preventDefault()
      go({ name: 'r.1.1' })
    }
  }
}
</script>

<style lang="sass">
.q-tabs.vertical-tabs
  margin-bottom: 0
.tabs-demo .q-tabs
  margin-bottom: 24px
.tabs-demo .q-toolbar .q-tabs
  margin-bottom: 0

.r-link
  display: block
  text-align: center
  text-decoration: none
  color: black
  padding: 2px
  border: 1px solid black

  &--active
    background-color: #ee9

  &--exact-active
    background-color: #9e9
</style>
