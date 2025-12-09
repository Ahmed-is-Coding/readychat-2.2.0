# ReadyChat 2.2.0 - Complete Documentation

## Table of Contents
1. [Project Overview](#project-overview)
2. [System Requirements](#system-requirements)
3. [Installation Guide](#installation-guide)
4. [Project Structure](#project-structure)
5. [Key Features](#key-features)
6. [File Descriptions](#file-descriptions)
7. [Configuration](#configuration)
8. [Database Setup](#database-setup)
9. [User Management](#user-management)
10. [Admin Panel](#admin-panel)
11. [Security Features](#security-features)
12. [Customization](#customization)
13. [Troubleshooting](#troubleshooting)
14. [Upgrade Information](#upgrade-information)

---

## Project Overview

**ReadyChat 2.2.0** is a PHP-based AJAX chat room application that enables real-time communication between users. It provides:

- **Real-time messaging** in multiple chat rooms
- **User authentication** with member and guest accounts
- **Private messaging** between users
- **Admin control panel** for managing users, rooms, and settings
- **User profiles** with avatar support
- **Game integration** for entertainment
- **Responsive design** with multiple templates

**Version:** 2.2.0  
**Type:** Web-based PHP/AJAX Application  
**Database:** MySQL  
**Architecture:** Session-based with AJAX communication

---

## System Requirements

### Server Requirements
- **PHP:** 5.0 or higher
- **MySQL:** 5.0 or higher
- **Apache/Server:** Any server supporting PHP and MySQL
- **Disk Space:** Minimum 50MB (including templates and libraries)

### Client Requirements
- **Browser:** Modern browser with JavaScript enabled
- **Connection:** Stable internet connection
- **Cookies:** Must be enabled for session management

### File Permissions
The following folders must be **writable (CHMOD 777)**:
- `core/` - Configuration files storage
- `template/avatars/uploads/` - User avatar uploads
- `install/` - Installation process

---

## Installation Guide

### Step 1: Upload Files
1. Download all files from the ReadyChat zip
2. Upload to your web server or local directory
3. Create a subdirectory (optional): `site.com/chat/` or place in root

### Step 2: Set Permissions
Before installation, ensure folder permissions:

```
chmod 777 core/
chmod 777 template/avatars/uploads/
chmod 777 install/
```

### Step 3: Run Installation
1. Navigate to: `http://yoursite.com/install/` (or `http://yoursite.com/chat/install/` if in subdirectory)
2. You should see the installation wizard automatically
3. If not, manually go to the install folder

### Step 4: Configure MySQL
**Database Credentials Required:**
- **Host:** Database server address (usually `localhost`)
- **Username:** MySQL username
- **Password:** MySQL password
- **Database Name:** Name of your database

**Password Key:**
- Create a unique string of numbers and letters
- This encrypts user passwords uniquely
- Store this safely - you'll need it if you reinstall

### Step 5: Create Admin Account
- During installation, create the administrator account
- This account has full control over the chat system
- Username and password will be set during setup

### Step 6: Verify Installation
- Remove write permissions from `install/` folder after completion
- CHMOD install/ to 755 or 644
- Database tables are automatically created
- Application is ready to use

### Step 7: Access the Chat
- Navigate to: `http://yoursite.com/` (or subdirectory)
- Login with your admin or user account
- Start chatting!

---

## Project Structure

### Root Files
```
index.php                 # Main chat interface entry point
login.php                # User login page
logout.php               # User logout handler
register.php             # New user registration
profile.php              # User profile management
private_chat.php         # Private messaging interface
upload.php               # File/avatar upload handler
banned.php               # Banned users page
arcade.php               # Game/entertainment section
```

### /core - Core Application Files
```
readyChat.js             # Main JavaScript chat functions
private.js               # Private messaging JavaScript
rc.cmd.php              # Chat command processor
rc.emoticons.js         # Emoticon/emoji handler
rc.language.js          # Language/localization support
rc.listings.php         # User/room listing generator
rc.loadProfile.php      # Load user profile data
rc.loadRoom.php         # Load room data
rc.notify.php           # Notification system
rc.privateMain.php      # Private chat main handler
rc.privateSend.php      # Private message sender
rc.profile.js           # Profile JavaScript
rc.profileSave.php      # Save profile changes
rc.roomList.php         # Generate room list
rc.sendChat.php         # Process chat messages
rc.swapRoom.php         # Switch between rooms
paginate.php            # Pagination helper
/rc/                    # Configuration folder
  ├── config.inc.php    # Main configuration file
  ├── database.inc.php  # Database credentials
  └── functions.inc.php # Global functions library
```

### /admin - Administration Panel
```
index.php               # Admin dashboard
adminjs.js              # Admin JavaScript functions
/pages/                 # Admin pages
  ├── dashboard.php     # System overview
  ├── users.php         # Manage users
  ├── rooms.php         # Manage chat rooms
  ├── games.php         # Manage games
  ├── history.php       # View chat history
  ├── settings.php      # System settings
  └── credits.php       # Credits page
/news/                  # News/updates section
  ├── news.html
  ├── version.html
  └── read me.txt
/docs/                  # Documentation
  ├── commands.html     # Chat commands
  ├── rooms.html        # Room documentation
  ├── users.html        # User management
  ├── games.html        # Games documentation
  └── /images/
/template/              # Admin styling
  ├── style.css
  ├── /icons/
  └── /images/
```

### /template - User Interface Templates
```
/defaultTemplate/       # Default chat interface
  /css/
    ├── readyChatLogin.css      # Login page styles
    ├── readyChatMain.css       # Main chat styles
    ├── readyChatPrivate.css    # Private chat styles
    └── readyChatProfiles.css   # Profile styles
  /html/
    ├── index.html.php          # Main chat room interface
    ├── login.html.php          # Login form
    ├── register.html.php       # Registration form
    ├── profile.html.php        # User profile
    ├── editProfile.html.php    # Edit profile
    ├── privatechat.html.php    # Private messages
    ├── banned.html.php         # Banned message
    └── selectAvatar.html.php   # Avatar selection
  /icons/                # Icon files
  /images/               # Template images
  
/flex/                  # Alternative template (if available)
  /css/
  /html/
  /icons/
  /images/

/smilies/               # Emoticon/smile files
/avatars/               # User avatar directory
  /uploads/             # Uploaded avatars
```

### /library - Third-party Libraries
```
jquery.js               # jQuery framework
/3rdparty/
  └── emotify.js        # Emoticon library
/audio/                 # Audio files for notifications
```

### /install - Installation Files
```
index.php               # Installation step 1
index_2.php             # Installation step 2 (permissions)
index_3.php             # Installation step 3 (MySQL config)
index_4.php             # Installation step 4 (database setup)
index_5.php             # Installation step 5 (admin account)
index_6.php             # Installation step 6 (confirmation)
index_7.php             # Installation step 7 (completion)
install.txt             # Installation notes
/css/
  └── installer.css     # Installer styling
/icons/                 # Installation icons
/images/                # Installation images
```

### /documents - User Documentation
```
getting_started.html              # Setup guide
ReadyChat 2.2.0 Information.html   # General information
help.html                         # User help documentation
privacy.html                      # Privacy policy
terms.html                        # Terms of service
Additional Licence Terms.txt      # License information
/images/                          # Documentation images
```

### Version Files
```
2.2.0 Changelog.html              # Version 2.2.0 changes
Upgrade from 2.1 to 2.2/          # Upgrade package
  ├── HOW TO UPDATE YOUR READYCHAT.txt
  ├── -- CHANGED FILES --.txt
  └── [Upgrade files...]
```

---

## Key Features

### 1. **Real-time Chat Rooms**
- Multiple permanent chat rooms
- Customizable room settings
- Room capacity limits
- Room descriptions and topics

### 2. **User Management**
- Member registration and login
- Guest login option
- User profiles with avatars
- User ranking system (Admin, Moderator, Member, Guest)
- User online status tracking

### 3. **User Ranks/Roles**
- **Admin** (Rank 3+): Full system control
- **Moderator** (Rank 2): Can moderate rooms
- **Member** (Rank 1): Standard chat access
- **Guest** (Rank 0): Limited access chat

### 4. **Private Messaging**
- Send private messages to other users
- Message history
- User availability checking

### 5. **Admin Control Panel**
- User management (create, edit, delete, ban)
- Room management
- System settings configuration
- Chat history viewing
- Game management
- News/update posting

### 6. **Chat Features**
- Real-time messaging with AJAX
- Chat commands support
- Emoticon/emoji support
- Message formatting
- User mention system
- Spam protection

### 7. **Profile Management**
- User profiles with customizable information
- Avatar upload and selection
- Profile editing
- User statistics

### 8. **Security**
- CSRF token protection
- Session-based authentication
- Password encryption with unique salt
- Admin-only access to control panel
- Ban system for disruptive users

### 9. **Games/Entertainment**
- Integrated game system
- Game room/arcade
- Entertainment features

### 10. **Customization**
- Multiple template themes
- Customizable colors for user ranks
- Emoticon customization
- Language support framework

---

## File Descriptions

### Core Configuration Files

#### `core/rc/config.inc.php`
**Purpose:** Main application configuration loader

**Key Functions:**
- Initializes session management
- Connects to MySQL database
- Validates user/guest sessions
- Sets timezone
- Configures error reporting
- Loads global settings from database

**Key Variables:**
- `$config['ver_num']` - Application version (2.2.0)
- `$config['time']` - Current server time
- `$config['micro']` - Microsecond timestamp
- `$uSession` - User session flag
- `$gSession` - Guest session flag
- `$user` - Current user data array
- `$guest` - Current guest data array
- `$settings` - Global settings from database

**Usage:** Included in every page that requires authentication

---

#### `core/rc/functions.inc.php`
**Purpose:** Global utility functions library

**Key Functions:**
- `activeUsers()` - Get list of active users in a room
- User list generation with rank indicators
- Inactive user timeout handling (idle kick)
- User status management
- Session verification

**User Rank Colors:**
- Rank 3 (Admin): Gold/special color
- Rank 2 (Moderator): Configurable color
- Rank 1 (Member): Default color
- Rank 0 (Guest): Default color

---

### Main Application Files

#### `index.php`
**Purpose:** Main chat room interface

**Key Functions:**
- Loads user session
- Updates user active status
- Validates room access
- Handles room capacity limits
- Loads chat room data
- Generates CSRF tokens
- Displays chat interface template

**Logic Flow:**
1. Check if user is logged in (user or guest)
2. Redirect to login if not authenticated
3. Update last active time
4. Check if user's room is valid
5. If room doesn't exist, move to default room
6. If room is full, move to default room
7. Generate security tokens
8. Load appropriate template

---

#### `login.php`
**Purpose:** User authentication page

**Key Functions:**
- User login form
- Guest login option
- Session creation
- Credential validation
- Form security tokens

---

#### `register.php`
**Purpose:** New user registration

**Key Functions:**
- Registration form
- Username availability checking
- Password validation
- Email verification (if configured)
- User account creation

---

#### `profile.php`
**Purpose:** User profile viewing and management

**Key Functions:**
- Display user profile information
- Edit profile details
- Avatar selection/upload
- Profile save functionality
- User statistics display

---

#### `private_chat.php`
**Purpose:** Private messaging interface

**Key Functions:**
- Private message display
- Message history
- New message handling
- User availability checking

---

#### `arcade.php`
**Purpose:** Game/entertainment section

**Key Functions:**
- Game display
- Game launcher
- Entertainment content

---

### AJAX/JavaScript Handler Files

#### `core/rc.sendChat.php`
**Purpose:** Processes chat messages via AJAX

**Key Functions:**
- Receives message from client
- Validates message content
- Checks for spam/flood
- Processes chat commands
- Emoticon conversion
- Database insertion
- Returns success/error response

---

#### `core/rc.privateMain.php`
**Purpose:** Loads private chat data

**Key Functions:**
- Fetches private message history
- Gets list of recent conversations
- Returns JSON response for AJAX

---

#### `core/rc.privateSend.php`
**Purpose:** Sends private messages

**Key Functions:**
- Validates recipient
- Checks if user is online
- Inserts message to database
- Returns delivery status
- Handles notifications

---

#### `core/rc.loadRoom.php`
**Purpose:** Loads chat room data

**Key Functions:**
- Gets room information
- Loads recent messages
- Gets active users list
- Returns room data as JSON

---

#### `core/rc.swapRoom.php`
**Purpose:** Changes active chat room

**Key Functions:**
- Validates new room
- Checks room capacity
- Updates user room assignment
- Returns new room data

---

#### `core/rc.cmd.php`
**Purpose:** Chat commands processor

**Key Functions:**
- Parses chat commands
- Executes appropriate actions
- Examples: `/whisper`, `/me`, `/shout`, etc.
- Returns command results

---

#### `core/rc.emoticons.js`
**Purpose:** Emoticon/emoji conversion

**Key Functions:**
- Converts text emoticons to images
- Emoticon selection
- Auto-replacement of smiley codes

**Common Emoticons:**
- `:)` - Happy face
- `:(` - Sad face
- `;)` - Wink
- `:D` - Big smile
- `:P` - Tongue out

---

### Admin Panel Files

#### `admin/index.php`
**Purpose:** Admin dashboard homepage

**Key Functions:**
- System overview
- Quick stats
- Recent activity
- Navigation to admin pages
- Admin functions menu

**Access Control:**
- User must have rank 2 or higher
- Only accessible to moderators and admins

---

#### `admin/pages/users.php`
**Purpose:** User management

**Key Features:**
- List all users
- Search users
- Create new users
- Edit user information
- Delete users
- Ban/unban users
- Promote/demote users
- Reset passwords
- View user activity

**Admin Actions:**
- Change user rank
- Modify user rooms
- Edit user profiles
- Ban disruptive users
- Delete inactive accounts

---

#### `admin/pages/rooms.php`
**Purpose:** Chat room management

**Key Features:**
- Create new rooms
- Edit room settings
- Delete rooms
- Set room capacity limits
- Set default room
- Manage room descriptions
- View room activity
- Room access control

---

#### `admin/pages/settings.php`
**Purpose:** System configuration

**Key Settings:**
- Site title/name
- Default room selection
- Idle timeout duration
- Max users per room
- Emoticon settings
- Mod color settings
- Privacy settings
- Email settings

---

#### `admin/pages/dashboard.php`
**Purpose:** System statistics and overview

**Key Displays:**
- Total users
- Active users
- Chat rooms count
- Messages today
- System status
- Database size
- Last activities

---

#### `admin/pages/history.php`
**Purpose:** Chat message history

**Key Features:**
- View all chat messages
- Search/filter messages
- Sort by user/room/date
- Delete messages
- View message details
- Moderation tools

---

#### `admin/pages/games.php`
**Purpose:** Game/arcade management

**Key Features:**
- List available games
- Add new games
- Remove games
- Configure games
- Game settings
- Game statistics

---

### Template Files

#### `template/defaultTemplate/html/index.html.php`
**Purpose:** Main chat room interface template

**Key Elements:**
- Chat message display area
- User list sidebar
- Message input form
- Room selector
- User menu
- Online status indicator

**JavaScript Integration:**
- Auto-refresh message list
- Real-time user updates
- Message submission
- Room switching
- Private message notifications

---

#### `template/defaultTemplate/html/login.html.php`
**Purpose:** Login form template

**Key Elements:**
- Username field
- Password field
- Remember me checkbox
- Login button
- Register link
- Guest login option

---

#### `template/defaultTemplate/html/profile.html.php`
**Purpose:** User profile display template

**Key Elements:**
- User information display
- Avatar display
- Join date
- Message count
- Activity status
- Edit profile button

---

#### `template/defaultTemplate/css/readyChatMain.css`
**Purpose:** Main chat interface styling

**Key Styles:**
- Chat message display
- User list formatting
- Input area styling
- Room list appearance
- Color schemes
- Responsive layout

---

---

## Configuration

### Database Configuration (`core/rc/database.inc.php`)

This file contains your database connection credentials:

```php
<?php
    // Database credentials - SET DURING INSTALLATION
    define('DB_HOST', 'localhost');      // Database server
    define('DB_USER', 'username');       // Database user
    define('DB_PASS', 'password');       // Database password
    define('DB_NAME', 'readychat');      // Database name
    define('ENCRYPT_KEY', 'uniquekey');  // Password encryption key
    define('installed', true);            // Installation flag
?>
```

**Important:** 
- These settings are created during installation
- Do not share this file
- Keep `ENCRYPT_KEY` private
- If you lose this, you won't be able to recover passwords

---

### Main Configuration (`core/rc/config.inc.php`)

**Key Configuration Items:**

1. **Session Management**
   - Session start: `session_start()`
   - Session variables: `$_SESSION["readyChatUser"]`, `$_SESSION["readyChatGuest"]`

2. **User Sessions**
   - `$uSession` - Flag for user login (1 if logged in)
   - `$gSession` - Flag for guest login (1 if logged in)

3. **Security Tokens**
   - `$_SESSION["post_key"]` - CSRF token for forms
   - `$_SESSION["admin_key"]` - Admin operation token

4. **Global Arrays**
   - `$user` - Current user's data from database
   - `$guest` - Current guest's data from database
   - `$settings` - Site-wide settings from database

5. **Time Configuration**
   - Timezone: `date_default_timezone_set('Europe/London')`
   - Adjust as needed for your location

---

### Settings Table (Database)

The `settings` table stores site-wide configuration:

**Key Settings:**
- `site_title` - Website/chat name
- `default_room` - Default room ID for new users
- `idle_kick` - Minutes before idle timeout
- `mod_hex` - Hex color for moderator names
- `admin_hex` - Hex color for admin names
- `room_limit` - Max users per room
- `full_exempt` - Allow admins to join full rooms (1/0)
- `private_chat_enabled` - Enable private messaging (1/0)
- `guest_enabled` - Allow guest login (1/0)

---

## Database Setup

### Database Tables

#### `users` Table
Stores registered member accounts

**Columns:**
- `user_id` (INT) - Primary key, auto-increment
- `user_name` (VARCHAR) - Username (unique)
- `password` (VARCHAR) - Encrypted password
- `email` (VARCHAR) - User email
- `user_room` (INT) - Current room ID
- `rank` (INT) - User rank (0-3)
- `avatar` (VARCHAR) - Avatar filename
- `profile` (TEXT) - User profile info
- `status` (VARCHAR) - User status message
- `active` (INT) - Is user currently online (1/0)
- `last_active` (INT) - Last activity timestamp
- `date_joined` (DATETIME) - Account creation date
- `last_login` (DATETIME) - Last login time
- `banned` (INT) - Is user banned (1/0)
- `ban_reason` (TEXT) - Ban reason if banned

**Indexes:**
- PRIMARY KEY: `user_id`
- UNIQUE KEY: `user_name`
- INDEX: `rank`, `active`, `user_room`

---

#### `guests` Table
Stores guest session data

**Columns:**
- `guest_id` (INT) - Primary key
- `guest_name` (VARCHAR) - Guest username
- `guest_room` (INT) - Guest's current room
- `active` (INT) - Is guest online (1/0)
- `last_active` (INT) - Last activity timestamp
- `date_joined` (DATETIME) - Session start time

---

#### `rooms_permanent` Table
Stores permanent chat rooms

**Columns:**
- `room_id` (INT) - Primary key, auto-increment
- `room_name` (VARCHAR) - Room name
- `room_topic` (VARCHAR) - Room description/topic
- `room_limit` (INT) - Max users allowed
- `icon` (VARCHAR) - Room icon filename
- `created_date` (DATETIME) - Creation date
- `visible` (INT) - Is room visible (1/0)

---

#### `messages` Table
Stores chat messages

**Columns:**
- `message_id` (INT) - Primary key, auto-increment
- `user_id` (INT) - User who sent message
- `room_id` (INT) - Room where sent
- `message_text` (TEXT) - Message content
- `message_time` (TIMESTAMP) - Send time
- `ip_address` (VARCHAR) - User's IP address

**Index:**
- INDEX: `room_id`, `message_time`

---

#### `private_messages` Table
Stores private messages between users

**Columns:**
- `message_id` (INT) - Primary key
- `sender_id` (INT) - Sending user ID
- `receiver_id` (INT) - Receiving user ID
- `message_text` (TEXT) - Message content
- `message_time` (TIMESTAMP) - Send time
- `read_status` (INT) - Has been read (1/0)

---

#### `settings` Table
Stores global site settings

**Columns:**
- `setting_id` (INT) - Primary key
- `setting_name` (VARCHAR) - Setting name
- `setting_value` (VARCHAR) - Setting value
- (Alternatively: individual columns for each setting)

---

#### `bans` Table
Stores user bans

**Columns:**
- `ban_id` (INT) - Primary key
- `user_id` (INT) - Banned user
- `reason` (TEXT) - Ban reason
- `banned_by` (INT) - Admin who banned
- `ban_date` (DATETIME) - When banned
- `unban_date` (DATETIME) - When to auto-unban (NULL = permanent)
- `ip_address` (VARCHAR) - Banned IP (optional)

---

#### `games` Table (Optional)
Stores arcade/game information

**Columns:**
- `game_id` (INT) - Primary key
- `game_name` (VARCHAR) - Game name
- `game_file` (VARCHAR) - Game file path
- `description` (TEXT) - Game description
- `enabled` (INT) - Is game active (1/0)

---

### Database Creation Process (Automatic)

During installation:
1. Installation script connects to MySQL
2. Verifies database exists
3. Creates all required tables automatically
4. Inserts default data (default room, admin user)
5. Stores configuration in `database.inc.php`

---

## User Management

### User Ranks/Roles System

#### Rank Levels
```
Rank 0: Guest
├─ Temporary login
├─ Limited room access
├─ Cannot use private chat (optional)
└─ No admin access

Rank 1: Member
├─ Full chat access
├─ Private messaging
├─ Profile customization
├─ Avatar upload
└─ Normal permissions

Rank 2: Moderator
├─ All member permissions
├─ Kick/ban users
├─ Delete messages
├─ Edit room settings
├─ User management
└─ Moderation tools

Rank 3+: Administrator
├─ All moderator permissions
├─ Access admin panel
├─ Manage users & ranks
├─ Create/delete rooms
├─ System settings
├─ View logs/history
└─ Full system control
```

### User Registration

**Registration Process:**
1. User goes to `register.php`
2. Fills out registration form:
   - Username (checked for uniqueness)
   - Email address
   - Password (encrypted with ENCRYPT_KEY)
   - Avatar selection (optional)
3. Form validated on both client and server
4. User data inserted into `users` table
5. Rank set to 1 (member) by default
6. User can then login

**Validation:**
- Username: 3-20 characters, alphanumeric
- Email: Valid email format
- Password: Minimum length requirement
- Avatar: Selected from available options

---

### User Login

**Login Process:**
1. User submits username & password on `login.php`
2. Credentials validated against `users` table
3. Password checked against encrypted version
4. Session created: `$_SESSION["readyChatUser"] = username`
5. User data loaded from database
6. Redirect to `index.php` (main chat)

**Guest Login:**
1. User selects "Login as Guest"
2. Guest name generated or user-provided
3. Session created: `$_SESSION["readyChatGuest"] = guestname`
4. Guest record inserted to `guests` table
5. Limited access to chat rooms

---

### User Logout

**Logout Process:**
1. User clicks logout button
2. Session destroyed: `unset($_SESSION["readyChatUser"])` or `unset($_SESSION["readyChatGuest"])`
3. Database updated: `active` set to 0
4. Redirect to `login.php`

---

### Profile Management

**Profile Features:**
- **Avatar Upload:** Users can upload custom avatars
  - Files stored in: `template/avatars/uploads/`
  - File size limit: Configurable
  - Allowed formats: JPG, PNG, GIF

- **Profile Information:**
  - Biography/about section
  - Location (optional)
  - Website (optional)
  - Custom status message

- **Profile Editing:**
  - Users can edit own profile via `profile.php`
  - Admins can edit any user profile
  - Changes saved immediately to database

---

### User Ban System

**Ban Types:**
1. **Temporary Ban**
   - User cannot login for specified duration
   - Auto-unban after time expires
   - Message shown about ban duration

2. **Permanent Ban**
   - User cannot login indefinitely
   - Can only be lifted by admin
   - Must contact admin for review

3. **IP Ban** (Optional)
   - Ban by IP address instead of user
   - Prevents account hopping
   - More severe enforcement

**Ban Process:**
1. Admin goes to admin panel > Users
2. Selects user to ban
3. Provides ban reason
4. Sets duration (temporary/permanent)
5. Confirmation applied
6. User record updated with ban status
7. User receives ban message on next login attempt

---

## Admin Panel

### Admin Access

**Location:** `admin/index.php`

**Access Requirements:**
- User rank must be 2 (Moderator) or higher (Admin)
- Login with admin account
- Cannot be accessed by regular members or guests

**Admin Dashboard:**
- System statistics
- Quick links to management sections
- Recent activity feed
- System status monitoring

---

### User Management (`admin/pages/users.php`)

**Features:**
- **View Users**
  - List all registered users
  - Filter by rank, status, room
  - Search by username
  - Pagination for large lists

- **Create User**
  - Admin creates new user accounts
  - Set initial rank
  - Assign to default room
  - Set password initially

- **Edit User**
  - Change username
  - Reset password
  - Change user rank
  - Modify profile info
  - Change avatar
  - Move to different room

- **Delete User**
  - Permanently remove user
  - Option to delete user's messages
  - Confirmation required

- **Ban/Unban**
  - Ban disruptive users
  - Set ban duration
  - Specify ban reason
  - View ban list
  - Unban users

- **Promote/Demote**
  - Change user rank
  - Grant moderator privileges
  - Revoke admin privileges

---

### Room Management (`admin/pages/rooms.php`)

**Features:**
- **View Rooms**
  - List all chat rooms
  - See room stats (users online, messages)
  - View room settings
  - Room visibility status

- **Create Room**
  - Create new chat room
  - Set room name
  - Set topic/description
  - Set user capacity limit
  - Choose room icon
  - Set visibility (public/private)

- **Edit Room**
  - Modify room name
  - Update topic/description
  - Change capacity limits
  - Change icon
  - Toggle visibility

- **Delete Room**
  - Remove room from system
  - Option to move users to default room
  - Confirmation required

- **Set Default Room**
  - Choose which room new users join
  - Where users are moved if room full

---

### System Settings (`admin/pages/settings.php`)

**Configurable Settings:**
- **Basic Settings**
  - Site title/name
  - Site description
  - Admin email

- **Chat Settings**
  - Default room selection
  - Max users per room limit
  - Idle timeout duration (minutes)
  - Allow full-room exemption for admins

- **User Settings**
  - Allow guest login
  - Require email verification
  - Username length limits
  - Password requirements

- **Display Settings**
  - Theme selection
  - Moderator color (hex code)
  - Admin color (hex code)
  - Messages per page
  - Emoticons enabled

- **Privacy Settings**
  - Private messaging enabled
  - User profiles visible
  - Profile editing allowed
  - Show active user list

- **Security Settings**
  - CSRF token validation
  - Session timeout
  - IP tracking
  - Flood protection

---

### Chat History (`admin/pages/history.php`)

**Features:**
- **View Messages**
  - Display all chat messages
  - Show date, time, user, room
  - Message content
  - Full search/filtering

- **Search**
  - Search by username
  - Search by room
  - Search by date range
  - Search by keyword in message

- **Moderation**
  - Delete inappropriate messages
  - Hide messages from view
  - Flag messages for review
  - View deleted messages log

- **Analytics**
  - Most active rooms
  - Most chatty users
  - Peak chat times
  - Message statistics

---

### Games Management (`admin/pages/games.php`)

**Features:**
- **View Games**
  - List all available games
  - See game descriptions
  - Status (enabled/disabled)
  - Usage statistics

- **Add Game**
  - Upload game file
  - Set game name
  - Add description
  - Configure game settings
  - Set enabling status

- **Edit Game**
  - Modify game description
  - Update game file
  - Change settings
  - Enable/disable game

- **Delete Game**
  - Remove game from arcade
  - Confirmation required

---

## Security Features

### CSRF Protection (Cross-Site Request Forgery)

**Implementation:**
1. Token generation on each page load
2. Token stored in session: `$_SESSION["post_key"]`
3. Token included in all forms as hidden field
4. Token validated on form submission
5. Invalid/missing token rejects request

**Code Example:**
```php
// Generate token
$_SESSION["post_key"] = sha1(rand(323, 4000));
$post_key = md5($_SESSION["post_key"]);

// In form
<input type="hidden" name="post_key" value="<?php echo $post_key; ?>" />

// Validate on submission
if ($_POST["post_key"] != $post_key) {
    die("Security token invalid");
}
```

---

### Session Security

**Session Management:**
- Sessions stored server-side
- Session ID in cookie (not URL)
- Session timeout after idle period
- Automatic session regeneration
- User verification on each request

**Session Variables:**
- `$_SESSION["readyChatUser"]` - Authenticated user
- `$_SESSION["readyChatGuest"]` - Guest session
- `$_SESSION["post_key"]` - CSRF token
- `$_SESSION["admin_key"]` - Admin operations token

---

### Password Security

**Encryption:**
- Passwords encrypted with custom key: `ENCRYPT_KEY`
- Each password has unique salt
- Encryption uses PHP's `md5()` or similar
- Even admin cannot recover original passwords
- Password reset generates new encrypted password

**Password Requirements:**
- Minimum 6-8 characters (configured)
- Mix of numbers and letters recommended
- No plain text storage
- One-way encryption (cannot be decrypted)

---

### SQL Injection Prevention

**Protection Methods:**
- Use of `mysqli_real_escape_string()` for input
- Prepared statements recommended
- Input validation on all user inputs
- Type casting for numeric values

**Examples:**
```php
// Input escaping
$username = $mysqli->real_escape_string($_POST['username']);

// Safe query
$query = "SELECT * FROM users WHERE username = '$username'";
```

---

### Ban System

**Purpose:** Prevent disruptive users from accessing the system

**Mechanism:**
- User ranks checked on every page load
- Banned users cannot login
- IP bans prevent reconnection attempts
- Ban reason displayed to banned user
- Moderators can lift temporary bans

---

### Access Control

**Role-Based Access:**
- Guest: View only, limited rooms
- Member: Full chat access
- Moderator: Moderation tools, user management
- Admin: Complete system control

**Protected Pages:**
- Admin panel (rank check)
- Settings (admin only)
- User management (admin/moderator)
- Profile editing (own or admin)

---

## Customization

### Template Customization

**Template Locations:**
- Default: `template/defaultTemplate/`
- Alternative: `template/flex/`

**Template Structure:**
```
/template/[template-name]/
├── /css/           # Stylesheet files
├── /html/          # HTML template files (.php)
├── /icons/         # Icon images
└── /images/        # Template images
```

### Changing Themes

**How to Switch Templates:**
1. Open `core/rc/config.inc.php`
2. Find: `$template_name = "defaultTemplate";`
3. Change to: `$template_name = "flex";`
4. Save and reload chat

### Customizing Styles

**Main Style Files:**
- `template/[name]/css/readyChatMain.css` - Main chat styles
- `template/[name]/css/readyChatLogin.css` - Login styles
- `template/[name]/css/readyChatPrivate.css` - Private chat styles
- `template/[name]/css/readyChatProfiles.css` - Profile styles

**Common Customizations:**
- Change colors in CSS
- Modify fonts and sizes
- Adjust layout widths
- Change button styles
- Customize input fields

---

### Adding Emoticons/Smilies

**Emoticon Location:** `template/smilies/`

**How to Add:**
1. Create 20x20 pixel PNG image
2. Name convention: `[code].png`
   - Example: `happy.png` for `:)`
3. Add to smilies folder
4. Update emoticon mapping in JavaScript

**Emoticon JavaScript:** `core/rc.emoticons.js`

---

### Creating Custom Rooms

**Via Admin Panel:**
1. Go to: Admin Panel > Rooms > Create Room
2. Enter room name
3. Enter room topic/description
4. Set user capacity limit
5. Select room icon
6. Set visibility
7. Click Create

**Users** will see room in room list and can join

---

### User Rank Colors

**Customization in Settings:**
- Admin Panel > Settings
- Find "Moderator Color" (hex code)
- Find "Admin Color" (hex code)
- Example colors:
  - Gold: `#FFD700`
  - Red: `#FF0000`
  - Blue: `#0000FF`
  - Green: `#008000`

**In Database:**
- `settings` table
- `mod_hex` field for moderator color
- `admin_hex` field for admin color

---

### Changing Site Name/Title

**Via Admin Panel:**
1. Admin Panel > Settings
2. Find "Site Title"
3. Enter new name
4. Save settings

**Or in Database:**
1. Open `settings` table
2. Find `site_title` row
3. Update `setting_value`
4. Save changes

---

## Troubleshooting

### Installation Issues

**Problem: "Installation wizard not found"**
- Solution: Navigate to `/install/index.php` manually
- Check URL: `http://yoursite.com/install/`

**Problem: "Folder permissions error"**
- Solution: CHMOD these folders to 777:
  - `chmod 777 core/`
  - `chmod 777 template/avatars/uploads/`
  - `chmod 777 install/`
- Check with hosting provider if you can't change permissions

**Problem: "MySQL connection failed"**
- Verify database credentials are correct
- Check database server is running
- Confirm username/password are valid
- Check database name exists
- Firewall may be blocking connection

**Problem: "Unable to create tables"**
- Check database user has CREATE TABLE permission
- Check database is empty or compatible
- Verify MySQL version is 5.0+

---

### Login Issues

**Problem: "Login fails with correct password"**
- Check `database.inc.php` exists and has credentials
- Check user account created in database
- Check user not banned
- Verify cookies enabled in browser

**Problem: "Session expires immediately"**
- Check `$_SESSION["readyChatUser"]` is being set
- Verify `config.inc.php` is included correctly
- Check PHP session handling in php.ini

**Problem: "Cannot login as guest"**
- Verify guest login enabled in settings
- Check `guests` table exists
- Verify table permissions

---

### Database Issues

**Problem: "Database connection error"**
- Verify `database.inc.php` has correct credentials
- Check MySQL server is running
- Verify firewall allows connection
- Check database exists
- Try testing connection separately

**Problem: "Table doesn't exist"**
- Run installation again or manually create tables
- Check database was selected correctly
- Verify installation completed

**Problem: "Lost database.inc.php"**
- Reinstall and reconfigure MySQL
- Or manually recreate file with credentials
- Cannot recover encrypted passwords

---

### Chat Not Updating

**Problem: "Messages not appearing"**
- Check JavaScript console for errors
- Verify jQuery is loading
- Check AJAX requests in browser network tab
- Verify `rc.sendChat.php` is accessible
- Check message content isn't empty

**Problem: "Users list not updating"**
- Verify active users query working
- Check user's `last_active` time being updated
- Look for inactive user timeout issues
- Check `idle_kick` setting not too aggressive

---

### Private Chat Issues

**Problem: "Cannot send private messages"**
- Verify private messaging enabled in settings
- Check recipient is online
- Verify `rc.privateSend.php` accessible
- Check `private_messages` table exists
- Check user isn't blocked

**Problem: "Private messages not loading"**
- Verify `rc.privateMain.php` working
- Check browser console for errors
- Verify recipient exists
- Check database query permissions

---

### Avatar Upload Issues

**Problem: "Avatar upload fails"**
- Check `template/avatars/uploads/` is writable
- Verify `upload.php` is accessible
- Check file size limits
- Verify allowed file types (jpg, png, gif)
- Check disk space on server

**Problem: "Avatar doesn't display"**
- Verify image file uploaded correctly
- Check file permissions in upload folder
- Verify correct path in profile
- Check image file integrity

---

### Admin Panel Issues

**Problem: "Cannot access admin panel"**
- Verify user rank is 2 or higher
- Check login session valid
- Verify `admin/index.php` accessible
- Check admin rank in database

**Problem: "Settings changes not saving"**
- Verify `settings` table writable
- Check update query executing
- Verify CSRF token valid
- Check database permissions

---

### Performance Issues

**Problem: "Chat is slow/sluggish"**
- Check server CPU/memory usage
- Verify database indexes created
- Check for excessive active users
- Look for long-running queries
- Consider reducing auto-refresh frequency

**Problem: "Database is slow"**
- Check for missing indexes
- Verify tables aren't too large
- Archive old messages
- Check MySQL settings
- Monitor connection count

---

### File Permission Issues

**Problem: "Cannot write to folder"**
- Use CHMOD: `chmod 777 foldername`
- Check FTP user has write access
- Verify not in read-only filesystem
- Check disk space available
- Contact hosting for permission issues

---

## Upgrade Information

### Upgrading from 2.1 to 2.2

**Package Contents:**
- `HOW TO UPDATE YOUR READYCHAT.txt` - Step-by-step instructions
- `-- CHANGED FILES --.txt` - List of modified files
- Upgrade folder with changed files

**Upgrade Steps:**

1. **Backup Current Installation**
   - Backup entire `readyChat` folder
   - Backup database using phpMyAdmin
   - Save `database.inc.php` separately

2. **Review Changed Files**
   - Open `-- CHANGED FILES --.txt`
   - Note which files are updated
   - Check custom modifications

3. **Upload Changed Files**
   - Upload files from upgrade package
   - Overwrite existing files
   - Don't delete any files

4. **Update Database**
   - Check for database migrations
   - Run SQL updates if provided
   - Verify tables created/modified

5. **Test Installation**
   - Login to chat
   - Verify all features working
   - Check admin panel functions
   - Test user registration

6. **Resolve Issues**
   - Reapply custom modifications
   - Check file permissions
   - Clear browser cache if issues

---

### Version Information

**2.2.0 Changes:**
- See `2.2.0 Changelog.html` for full list
- Includes bug fixes and improvements
- New features in core system
- Database optimizations
- Security enhancements

**2.1 vs 2.2 Differences:**
- Upgraded AJAX functionality
- Improved message handling
- Enhanced user interface
- Better admin tools
- Security improvements
- Performance optimizations

---

### Backup & Restore

**Creating Backups:**
1. Download entire installation
2. Export MySQL database
3. Store safely offline
4. Document version number

**Restoring from Backup:**
1. Upload files to server
2. Import database dump
3. Verify credentials
4. Test login/functionality

---

## Quick Reference

### Useful File Paths
```
Main Chat: /index.php
Login: /login.php
Admin Panel: /admin/index.php
Settings: /admin/pages/settings.php
Users: /admin/pages/users.php
Rooms: /admin/pages/rooms.php
Database Config: /core/rc/database.inc.php
Main Config: /core/rc/config.inc.php
Template CSS: /template/[name]/css/
Template HTML: /template/[name]/html/
```

### Key Database Tables
```
users - Member accounts
guests - Guest sessions
rooms_permanent - Chat rooms
messages - Chat messages
private_messages - Private chats
settings - Site configuration
bans - Banned users
games - Arcade games
```

### Common Tasks
- **Change theme:** Edit `$template_name` in config.inc.php
- **Add room:** Admin > Rooms > Create
- **Ban user:** Admin > Users > Ban
- **Change colors:** Admin > Settings > Rank Colors
- **View history:** Admin > History
- **Manage users:** Admin > Users
- **Configure system:** Admin > Settings

---

## Support & Resources

- **Official Documentation:** See `/documents/` folder
- **Installation Help:** `/documents/getting_started.html`
- **Chat Commands:** `/admin/docs/commands.html`
- **Changelog:** `2.2.0 Changelog.html`
- **Upgrade Guide:** `Upgrade from 2.1 to 2.2/HOW TO UPDATE YOUR READYCHAT.txt`

---

## License

**ReadyChat 2.2.0**
- See `documents/Additional Licence Terms.txt`
- See `documents/terms.html` for terms of service
- See `documents/privacy.html` for privacy policy

---

**Document Version:** 1.0  
**ReadyChat Version:** 2.2.0  
**Last Updated:** 2025  
**Status:** Complete
