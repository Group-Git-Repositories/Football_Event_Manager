# Tournament Management System - README

## What is this?

A C++ program that manages a **tournament** with teams, players, group stages, and knockout rounds using struct-based data structures.

## Main Features

| Feature | What it does |
|---------|--------------|
| Team Management | Add/register teams with department, year, section |
| Player Management | Add players to specific teams (max 10 per team) |
| Group Assignment | Assign 4 teams to each of 4 groups |
| Match Schedule | Display group stage matches (3 weeks) |
| Standings Update | Update wins, losses, draws, points for teams |
| Top Teams | Show top 2 teams from each group (8 total) |
| Knockout Stage | Display quarter-final, semi-final, final matchups |

## Data Structure

```cpp
struct Player {
    string name;        // Player name
};

struct Teams {
    string name;        // Team name
    string department;  // Department
    int section;        // Section
    int year;           // Year
    bool grouped;       // Already assigned to group?
    int win, lose, draw, played, points;  // Stats
    Player player[10];  // Max 10 players
    int numberOfPlayer; // Actual player count
};

struct group {
    string name;               // Group One, Two, Three, Four
    Teams groupTeam[4];        // 4 teams per group
};
```

**Maximum:** 16 teams total | 4 groups | 4 teams per group | 10 players per team

## How to Use

### Compile & Run
```bash
g++ tournament.cpp -o tournament
./tournament
```

### Menu Options (0-8)

| Option | Action |
|--------|--------|
| 1 | Add Team |
| 2 | Add Player to Team |
| 3 | Add Team to Group |
| 4 | Display Group Matches |
| 5 | Update Standings |
| 6 | Display Top Teams |
| 7 | Display Knockout Stage |
| 8 | Display All Teams & Players |
| 0 | Exit |

## Workflow Example

```
1. Add Teams → Add at least 4 teams
2. Add Players → Add players to each team
3. Add to Groups → Assign teams to Group One, Two, etc.
4. Display Matches → View scheduled matches
5. Update Standings → Enter wins/losses/points
6. View Top Teams → See top 2 from each group
7. View Knockout → See quarter-final matchups
```

## Tournament Format

### Group Stage
- **4 Groups** (Group One, Two, Three, Four)
- **4 Teams per group**
- **3 Match Weeks** (each team plays all others once)

### Knockout Stage
- **Quarter Finals** (8 teams)
- **Semi Finals** (4 winners)
- **Final** (2 winners)

## Important Notes

⚠️ **Add at least 4 teams** before assigning to groups  
⚠️ **Maximum 16 teams total**  
⚠️ **Maximum 10 players per team**  
⚠️ **Data is NOT saved** - lost when program exits  
⚠️ **Groups must be filled completely** (4 teams each)

## Sample Output

```
******** Main Menu ********
1. Add Team
2. Add Player
3. Add team to group
4. Display Group Matches
5. Update Standings
6. Display Top Teams
7. Display knockout stage
8. Display Teams and their players
0. Exit
Enter Your Choice: 1
How many teams do you want to add (Max: 16): 4
Enter the name of team 1: Eagles
Enter the department of team 1: CS
...
```

## Input Validation

The program includes validation for:
- Invalid number inputs
- Team capacity limits
- Duplicate group assignments
- Empty team/player lists
- Out-of-range selections

## Limitations

- Console-only interface
- No data persistence
- Fixed tournament structure (4 groups of 4)
- Manual standings updates required

## Potential Improvements

- Add file saving/loading
- Automatic point calculation from wins/draws
- Head-to-head tiebreakers
- Match result entry instead of manual stats
- GUI interface
- Database integration
