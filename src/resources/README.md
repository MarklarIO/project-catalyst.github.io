# Resources

<script>
  import card_data from './resource_cards.yaml'
  export default {
    data () {
      return {
        cards: card_data.content
      }
    }
  }
</script>
<CardGrid cards="this.cards"/>

