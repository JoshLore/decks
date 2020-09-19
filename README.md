# decks

Package decks provides a simple API for creating and customizing decks of cards in Go.

## Installation

```
go get github.com/joshlore/decks
```

## Quickstart

```go
// get a default, ordered deck of 52 cards
d, err := decks.New()
if err != nil {
  // handle error
}

// Make sure you specify a random seed before shuffling the deck
rand.Seed(time.Now().UnixNano())

// Shuffle deck of cards
d.Shuffle()

// draw cards
myHand := []decks.Card{}
myHand = append(myHand, d.Draw())
myHand = append(myHand, d.Draw())

// print hand
for _, c := range myHand {
  fmt.Println(c)git
}

// discard hand
d.InsertBottom(myHand)
```

[Try it on The Go Playground](https://play.golang.org/p/UxA3SAAuWPR)
