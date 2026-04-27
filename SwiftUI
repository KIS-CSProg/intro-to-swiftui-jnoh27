import SwiftUI

// The main screen of the app.
// In SwiftUI, a screen is usually represented as a "View" instead of a UIViewController.
struct ContentView: View {
    
    // This list stores the names of the elements.
    // The names must match the image asset names exactly.
    let elements = ["Carbon", "Gold", "Chlorine", "Sodium"]
    
    // @State allows SwiftUI to watch this value.
    // When this value changes, the screen automatically updates.
    @State private var currentElementIndex = 0
    
    // This controls what text appears under the image.
    // It starts as "?" because the answer is hidden at first.
    @State private var displayedAnswer = "?"
    
    var body: some View {
        VStack(spacing: 30) {
            
            // Displays the image for the current element.
            // Image(...) loads an image from Assets.xcassets.
            Image(currentElementName)
                .resizable()
                .scaledToFit()
                .frame(width: 250, height: 250)
            
            // Displays either "?" or the actual element name.
            Text(displayedAnswer)
                .font(.largeTitle)
                .bold()
            
            HStack(spacing: 20) {
                
                // Button replaces the old @IBAction showAnswer function.
                Button("Show Answer") {
                    showAnswer()
                }
                .buttonStyle(.borderedProminent)
                
                // Button replaces the old @IBAction next function.
                Button("Next Element") {
                    goToNextElement()
                }
                .buttonStyle(.bordered)
            }
        }
        .padding()
    }
    
    // A computed property that returns the name of the current element.
    // This keeps the code cleaner because we do not repeat:
    // elements[currentElementIndex]
    var currentElementName: String {
        elements[currentElementIndex]
    }
    
    // Reveals the answer by changing the displayed text.
    // Because displayedAnswer is marked with @State,
    // SwiftUI refreshes the Text view automatically.
    func showAnswer() {
        displayedAnswer = currentElementName
    }
    
    // Moves to the next element in the list.
    func goToNextElement() {
        currentElementIndex += 1
        
        // If the index goes past the end of the list,
        // return to the first element.
        if currentElementIndex >= elements.count {
            currentElementIndex = 0
        }
        
        resetAnswer()
    }
    
    // Hides the answer again whenever the element changes.
    func resetAnswer() {
        displayedAnswer = "?"
    }
}

#Preview {
    ContentView()
}
