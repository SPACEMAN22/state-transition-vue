# state-transition-vue
HTML
<div id="app">
  <dot :show="showDot" :toggle="toggleDot"/>
</div>
Javascript/Vue
const dot = {
	props: ['show', 'toggle'],
	template: `
  	<transition name="fade" mode="out-in">
      <div class="circle" v-if="show" @click="toggle">
      </div>
    	<button v-else @click="toggle">
    		Show
 	 		</button>
    </transition>
  `
}
VUE
new Vue({
	el: '#app',
  data() {
  	return {
    	showDot: false
    }
  },
  components: {
  	dot
  },
  methods: {
  	toggleDot() {
    	this.showDot = !this.showDot;
    }
  }
});
CSS
.circle {
  width: 100px;
  height: 100px;
  border-radius: 10%;
  background: pink;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity .1s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
