const Home = {
    template: 
    `<div>
        <h3 class="font-weight-light">Vue Starter</h3>
        <h6 class="mb-3">Simple app with Vue router &amp; component examples😎</h6>
        <div>
            This example also references Bootstrap (optional) 
            for styling. Checkout the <code>Navbar</code> 
            component to see how the router-link is used to 
            set the active route. <code>Navbar</code> also shows
            how to pass data from parent-to-child using the 
            <code>loggedIn</code> prop.
        </div>
    </div>`
}

const Component1 = {
    template:
    `<div>
        <h3 class="font-weight-light">Page 1</h3>
        <div>Page 1 content...</div>
    </div>`
}

const NotFound = {
    template:
    `<div>
        <h3 class="font-weight-light">404</h3>
        <div>Not found</div>
    </div>`
}

const routes = [
    { path: '', component: Home },
    { path: '/1', component: Component1 },
    { path: '*', component: NotFound },
]

const router = new VueRouter({
    routes,
    linkExactActiveClass: 'active',
})

Vue.component('navbar', {
    template: '#navbar',
    props: {
        loggedIn: Boolean
    },
    methods: {
        toggleLogin() {
            this.loggedIn = !this.loggedIn
        }
    }
})

new Vue({
    router: router,
    el: "#app"
})
