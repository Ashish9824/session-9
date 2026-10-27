# session-9

### Task 1: 1D Array for Weekly Daily Steps

```c
#include <stdio.h>

int main() {
    // Declare and initialize a 1D array with 7 elements (Monday to Sunday)
    int dailySteps[7] = {6500, 7200, 5800, 8100, 6900, 10200, 9400};
    const char *days[7] = {
        "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"
    };

    printf("--- Weekly Step Count ---\n");
    // Traverse the 1D array using a for loop
    for (int i = 0; i < 7; i++) {
        printf("%-10s: %d steps\n", days[i], dailySteps[i]);
    }

    return 0;
}

```

---

### Task 2: 2D Array for Playlist Ratings Over 5 Days

A 2D array with 3 rows (playlists) and 5 columns (days). The second playlist corresponds to index `1`.

```c
#include <stdio.h>

int main() {
    // 2D Array: 3 rows (Playlists), 5 columns (Days)
    float playlistRatings[3][5] = {
        {4.2f, 4.3f, 4.1f, 4.5f, 4.4f}, // Playlist 1
        {4.8f, 4.9f, 4.7f, 5.0f, 4.9f}, // Playlist 2
        {3.8f, 3.9f, 4.0f, 4.1f, 4.0f}  // Playlist 3
    };

    printf("--- Ratings for Second Playlist (Index 1) ---\n");
    // Traverse only row index 1 across all 5 columns (days)
    for (int day = 0; day < 5; day++) {
        printf("Day %d: %.1f ★\n", day + 1, playlistRatings[1][day]);
    }

    return 0;
}

```

---

### Task 3: Weekly Average Zomato Spend Function

```c
#include <stdio.h>

// Function definition to calculate average from a 1D array
float calculateAverageSpend(const int orders[], int length) {
    int total = 0;

    // Loop through the array to sum up order amounts
    for (int i = 0; i < length; i++) {
        total += orders[i];
    }

    // Cast total to float before dividing to prevent integer truncation
    return (float)total / length;
}

int main() {
    int weeklyOrders[7] = {240, 0, 350, 180, 520, 410, 290}; // 7 days of spend
    int days = 7;

    float average = calculateAverageSpend(weeklyOrders, days);

    printf("--- Weekly Zomato Expense Summary ---\n");
    for (int i = 0; i < days; i++) {
        printf("Day %d: ₹%d\n", i + 1, weeklyOrders[i]);
    }
    printf("------------------------------------\n");
    printf("Average Daily Spend: ₹%.2f\n", average);

    return 0;
}

```

---

### Task 4: Highest Score from Each IPL Match (2D Array)

In this 2D array, each row represents an IPL match, and columns represent the scores of Team 1 and Team 2:

```c
#include <stdio.h>

int main() {
    // Rows = Matches (4 matches), Columns = [Team 1 Runs, Team 2 Runs]
    int cricketScores[4][2] = {
        {185, 189}, // Match 1: MI vs CSK
        {215, 198}, // Match 2: RCB vs KKR
        {162, 160}, // Match 3: GT vs RR
        {224, 221}  // Match 4: SRH vs DC
    };
    int totalMatches = 4;

    printf("--- IPL Match Highest Scores ---\n");
    for (int match = 0; match < totalMatches; match++) {
        int highestScore = cricketScores[match][0];

        // Compare against team 2 score
        if (cricketScores[match][1] > highestScore) {
            highestScore = cricketScores[match][1];
        }

        printf("Match %d [Scores: %d vs %d] -> Highest Score: %d\n", 
               match + 1, 
               cricketScores[match][0], 
               cricketScores[match][1], 
               highestScore);
    }

    return 0;
}

```
