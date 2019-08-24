<template lang='pug'>
			v-container(fluid grid-list-md)
			
				v-alert(type='info') Cliquez sur une image :)
			
				v-dialog(v-model='dialog' fullscreen)
					v-btn(fixed fab top right
						color='rgba(0,0,0,0.25)' depressed dark
						@click='dialog = false')
							v-icon mdi-close
					v-carousel(v-model='carousel' height='100vh'
						:class='$vuetify.theme.dark ? "black" : "white"')
						v-carousel-item(v-for='image in images')
							v-img(:src='image' contain height='100vh')
								template(#placeholder)
									v-overlay(absolute)
										v-progress-circular(indeterminate)

				v-layout(wrap)
					v-flex(v-for='image, index in images'
						sm6)
						v-img(:src='image' height='33vh'
							@click.stop='activate(e, index)')
							template(#placeholder)
								v-overlay(absolute)
									v-progress-circular(indeterminate)
</template>

<script lang='coffee'>
export default
  methods:
    activate: (e, index) ->
      @carousel = index
      @dialog = on

  data: ->
    dialog: null
    carousel: null
    images: [
      'https://images.unsplash.com/photo-1562734893-5c8b95a62b38?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1511207538754-e8555f2bc187?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1563581410561-7debcf2b09c8?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1516214104703-d870798883c5?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1563224521-1764eef21f15?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1511497584788-876760111969?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1562476586-26fd477ad883?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1564751744313-665df972eec8?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1562245859-9de3fae76585?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
      'https://images.unsplash.com/photo-1519821172144-4f87d85de2a1?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ'
    ]
</script>