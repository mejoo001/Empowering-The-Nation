# Empowering-The-Nation
import React from 'react';
import {
  View,
  Text,
  TextInput,
  TouchableOpacity,
  Image,
  ScrollView,
  StyleSheet,
} from 'react-native';

import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import Icon from 'react-native-vector-icons/MaterialIcons';
import FontAwesome from 'react-native-vector-icons/FontAwesome';

const Stack = createNativeStackNavigator();

// ================= LOGIN SCREEN =================

function LoginScreen({ navigation }) {
  return (
    <View style={styles.container}>
      <Image
        source={{
          uri: 'https://cdn-icons-png.flaticon.com/512/2909/2909768.png',
        }}
        style={styles.logo}
      />

      <Text style={styles.label}>EMAIL</Text>

      <TextInput
        placeholder="ENTER YOUR EMAIL"
        placeholderTextColor="#999"
        style={styles.input}
      />

      <Text style={styles.label}>PASSWORD</Text>

      <TextInput
        placeholder="ENTER YOUR PASSWORD"
        placeholderTextColor="#999"
        secureTextEntry
        style={styles.input}
      />

      <TouchableOpacity>
        <Text style={styles.forgotText}>FORGOT PASSWORD?</Text>
      </TouchableOpacity>

      <TouchableOpacity
        style={styles.loginButton}
        onPress={() => navigation.navigate('Home')}>
        <Text style={styles.loginButtonText}>LOGIN</Text>
        <Icon name="arrow-forward" size={20} color="#fff" />
      </TouchableOpacity>
    </View>
  );
}

// ================= HOME SCREEN =================

function HomeScreen({ navigation }) {
  return (
    <ScrollView style={styles.homeContainer}>
      <View style={styles.topBar}>
        <Icon name="menu" size={30} color="#000" />
        <Text style={styles.homeTitle}>Home</Text>
        <Icon name="notifications-none" size={28} color="#000" />
      </View>

      <Image
        source={{
          uri: 'https://cdn-icons-png.flaticon.com/512/2909/2909768.png',
        }}
        style={styles.homeLogo}
      />

      <Text style={styles.bigTitle}>EMPOWERING</Text>
      <Text style={styles.bigTitle}>THE</Text>
      <Text style={styles.bigTitle}>NATION</Text>

      <Text style={styles.subHeading}>
        Skills Training For A Better Tomorrow
      </Text>

      <Text style={styles.description}>
        Empowering individuals with practical skills for better opportunities
        and a brighter future.
      </Text>

      <TouchableOpacity
        style={styles.courseButton}
        onPress={() => navigation.navigate('SixMonthCourses')}>
        <Text style={styles.courseButtonText}>6 - Month Course</Text>
      </TouchableOpacity>

      <TouchableOpacity
        style={styles.courseButton}
        onPress={() => navigation.navigate('SixWeekCourses')}>
        <Text style={styles.courseButtonText}>6 - Week Course</Text>
      </TouchableOpacity>
    </ScrollView>
  );
}

// ================= 6 MONTH COURSES =================

function SixMonthCourses({ navigation }) {
  return (
    <ScrollView style={styles.screenContainer}>
      <View style={styles.headerBar}>
        <Icon name="menu" size={28} color="#000" />

        <View style={styles.dropdownBox}>
          <Text style={styles.dropdownText}>6 - Month Courses</Text>
          <Icon name="keyboard-arrow-down" size={28} color="#000" />
        </View>
      </View>

      {monthCourses.map((item, index) => (
        <View key={index} style={styles.courseCard}>
          <Image source={{ uri: item.image }} style={styles.courseImage} />

          <View style={styles.courseInfo}>
            <Text style={styles.courseTitle}>{item.title}</Text>
            <Text style={styles.coursePrice}>{item.price}</Text>
            <Text style={styles.courseDescription}>{item.description}</Text>
          </View>

          <TouchableOpacity>
            <Icon name="add" size={30} color="#58a58c" />
          </TouchableOpacity>
        </View>
      ))}

      <View style={styles.bottomButtons}>
        <TouchableOpacity style={styles.backButton}>
          <Text style={styles.buttonText}>BACK</Text>
        </TouchableOpacity>

        <TouchableOpacity
          style={styles.nextButton}
          onPress={() => navigation.navigate('CalculateFees')}>
          <Text style={styles.buttonText}>NEXT</Text>
        </TouchableOpacity>
      </View>
    </ScrollView>
  );
}

// ================= 6 WEEK COURSES =================

function SixWeekCourses({ navigation }) {
  return (
    <ScrollView style={styles.screenContainer}>
      <View style={styles.headerBar}>
        <Icon name="menu" size={28} color="#000" />

        <View style={styles.dropdownBox}>
          <Text style={styles.dropdownText}>6 - Week Courses</Text>
          <Icon name="keyboard-arrow-down" size={28} color="#000" />
        </View>
      </View>

      {weekCourses.map((item, index) => (
        <View key={index} style={styles.courseCard}>
          <Image source={{ uri: item.image }} style={styles.courseImage} />

          <View style={styles.courseInfo}>
            <Text style={styles.courseTitle}>{item.title}</Text>
            <Text style={styles.coursePrice}>{item.price}</Text>
            <Text style={styles.courseDescription}>{item.description}</Text>
          </View>

          <TouchableOpacity>
            <Icon name="add" size={30} color="#58a58c" />
          </TouchableOpacity>
        </View>
      ))}

      <View style={styles.bottomButtons}>
        <TouchableOpacity style={styles.backButton}>
          <Text style={styles.buttonText}>BACK</Text>
        </TouchableOpacity>

        <TouchableOpacity
          style={styles.nextButton}
          onPress={() => navigation.navigate('CalculateFees')}>
          <Text style={styles.buttonText}>NEXT</Text>
        </TouchableOpacity>
      </View>
    </ScrollView>
  );
}

// ================= CALCULATE FEES =================

function CalculateFees({ navigation }) {
  return (
    <ScrollView style={styles.screenContainer}>
      <Text style={styles.calculateHeading}>Calculate Fees</Text>

      <Text style={styles.formLabel}>Name</Text>
      <TextInput placeholder="Enter your name" style={styles.formInput} />

      <Text style={styles.formLabel}>Phone Number</Text>
      <TextInput
        placeholder="Enter your phone number"
        style={styles.formInput}
      />

      <Text style={styles.formLabel}>Email Address</Text>
      <TextInput
        placeholder="Enter your email address"
        style={styles.formInput}
      />

      <Text style={styles.selectText}>Select Course</Text>

      <View style={styles.checkboxRow}>
        <View style={styles.checkbox} />
        <Text>First Aid (R1500)</Text>
      </View>

      <View style={styles.checkboxRow}>
        <View style={styles.checkbox} />
        <Text>Sewing (R1500)</Text>
      </View>

      <View style={styles.checkboxRow}>
        <View style={styles.checkbox} />
        <Text>Cooking (R1500)</Text>
      </View>

      <TouchableOpacity
        style={styles.calculateButton}
        onPress={() => navigation.navigate('QuoteSummary')}>
        <Text style={styles.calculateButtonText}>Calculate Quote</Text>
      </TouchableOpacity>

      <View style={styles.bottomButtons}>
        <TouchableOpacity style={styles.backButton}>
          <Text style={styles.buttonText}>BACK</Text>
        </TouchableOpacity>

        <TouchableOpacity style={styles.nextButton}>
          <Text style={styles.buttonText}>NEXT</Text>
        </TouchableOpacity>
      </View>
    </ScrollView>
  );
}

// ================= QUOTE SUMMARY =================

function QuoteSummary({ navigation }) {
  return (
    <View style={styles.screenContainer}>
      <Text style={styles.summaryHeading}>QUOTE SUMMARY</Text>

      <View style={styles.summaryBox}>
        <Text>Courses Selected (3)</Text>
        <Text>First Aid ....................... R1500</Text>
        <Text>Sewing ........................ R750</Text>
        <Text>Cooking ...................... R1500</Text>

        <View style={styles.line} />

        <Text>SUBTOTAL ................. R3750</Text>
        <Text>Discount (10%) ............ -R375</Text>
        <Text>Total After Discount ....... R3375</Text>
        <Text>VAT (15%) .................... R506.25</Text>

        <TouchableOpacity style={styles.totalQuoteButton}>
          <Text style={styles.totalQuoteText}>TOTAL QUOTE R3881.25</Text>
        </TouchableOpacity>
      </View>

      <TouchableOpacity style={styles.consultButton}>
        <Text style={styles.consultButtonText}>Request Consultant</Text>
      </TouchableOpacity>

      <View style={styles.bottomButtons}>
        <TouchableOpacity style={styles.backButton}>
          <Text style={styles.buttonText}>BACK</Text>
        </TouchableOpacity>

        <TouchableOpacity
          style={styles.nextButton}
          onPress={() => navigation.navigate('Contact')}>
          <Text style={styles.buttonText}>NEXT</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
}

// ================= CONTACT SCREEN =================

function ContactScreen() {
  return (
    <ScrollView style={styles.screenContainer}>
      <Text style={styles.contactHeading}>Contact</Text>

      <View style={styles.campusDropdown}>
        <Text>Sandton Campus</Text>
        <Icon name="keyboard-arrow-down" size={24} color="#000" />
      </View>

      <View style={styles.contactCard}>
        <FontAwesome name="map-marker" size={28} color="#000" />

        <Text style={styles.contactText}>
          123 Rivonia Road {'\n'}Sandton, Johannesburg {'\n'}2196
        </Text>
      </View>

      <TouchableOpacity style={styles.mapButton}>
        <Text style={styles.mapButtonText}>View Map</Text>
      </TouchableOpacity>

      <View style={styles.contactCard}>
        <FontAwesome name="phone" size={22} color="#000" />
        <Text style={styles.contactText}>011 123 4567</Text>
      </View>

      <View style={styles.contactCard}>
        <FontAwesome name="envelope-o" size={22} color="#000" />
        <Text style={styles.contactText}>
          info@empoweringthenation.co.za
        </Text>
      </View>

      <View style={styles.contactCard}>
        <FontAwesome name="clock-o" size={24} color="#000" />
        <Text style={styles.contactText}>
          Monday - Friday {'\n'}08h00 - 16h30
        </Text>
      </View>

      <View style={styles.bottomButtons}>
        <TouchableOpacity style={styles.backButton}>
          <Text style={styles.buttonText}>BACK</Text>
        </TouchableOpacity>

        <TouchableOpacity style={styles.nextButton}>
          <Text style={styles.buttonText}>EXIT</Text>
        </TouchableOpacity>
      </View>
    </ScrollView>
  );
}

// ================= COURSE DATA =================

const monthCourses = [
  {
    title: 'First Aid',
    price: '-R1500',
    description: 'Provide first aid support and basic life support.',
    image:
      'https://cdn-icons-png.flaticon.com/512/2966/2966481.png',
  },
  {
    title: 'Sewing',
    price: '-R1500',
    description: 'Learn sewing techniques and garment design.',
    image:
      'https://cdn-icons-png.flaticon.com/512/3082/3082037.png',
  },
  {
    title: 'Landscaping',
    price: '-R1500',
    description: 'Develop landscaping and gardening skills.',
    image:
      'https://cdn-icons-png.flaticon.com/512/427/427735.png',
  },
  {
    title: 'Life Skills',
    price: '-R1500',
    description: 'Improve communication and workplace readiness.',
    image:
      'https://cdn-icons-png.flaticon.com/512/3135/3135715.png',
  },
];

const weekCourses = [
  {
    title: 'Child Minding',
    price: '-R750',
    description: 'Basic childcare and safety skills.',
    image:
      'https://cdn-icons-png.flaticon.com/512/3048/3048122.png',
  },
  {
    title: 'Cooking',
    price: '-R750',
    description: 'Practical cooking and nutrition skills.',
    image:
      'https://cdn-icons-png.flaticon.com/512/706/706164.png',
  },
  {
    title: 'Garden Maintenance',
    price: '-R750',
    description: 'Learn gardening and maintenance basics.',
    image:
      'https://cdn-icons-png.flaticon.com/512/427/427735.png',
  },
];

// ================= APP NAVIGATION =================

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator screenOptions={{ headerShown: false }}>
        <Stack.Screen name="Login" component={LoginScreen} />
        <Stack.Screen name="Home" component={HomeScreen} />

        <Stack.Screen
          name="SixMonthCourses"
          component={SixMonthCourses}
        />

        <Stack.Screen
          name="SixWeekCourses"
          component={SixWeekCourses}
        />

        <Stack.Screen
          name="CalculateFees"
          component={CalculateFees}
        />

        <Stack.Screen
          name="QuoteSummary"
          component={QuoteSummary}
        />

        <Stack.Screen name="Contact" component={ContactScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

// ================= STYLES =================

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#f5f5f5',
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
  },

  logo: {
    width: 140,
    height: 140,
    marginBottom: 20,
  },

  label: {
    fontWeight: 'bold',
    marginTop: 10,
    marginBottom: 5,
    color: '#333',
  },

  input: {
    width: '85%',
    backgroundColor: '#fff',
    borderRadius: 12,
    padding: 14,
    marginBottom: 10,
  },

  forgotText: {
    color: '#b17eff',
    marginVertical: 10,
    fontSize: 12,
  },

  loginButton: {
    flexDirection: 'row',
    alignItems: 'center',
    justifyContent: 'center',
    backgroundColor: '#0f5f1f',
    width: 140,
    padding: 14,
    borderRadius: 30,
    marginTop: 15,
  },

  loginButtonText: {
    color: '#fff',
    fontWeight: 'bold',
    marginRight: 10,
  },

  homeContainer: {
    flex: 1,
    backgroundColor: '#f5f5f5',
    padding: 20,
  },

  topBar: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    alignItems: 'center',
    marginTop: 20,
  },

  homeTitle: {
    backgroundColor: '#8cb6a2',
    paddingHorizontal: 30,
    paddingVertical: 8,
    borderRadius: 10,
    fontWeight: 'bold',
  },

  homeLogo: {
    width: 140,
    height: 140,
    alignSelf: 'center',
    marginTop: 20,
  },

  bigTitle: {
    textAlign: 'center',
    fontWeight: 'bold',
    fontSize: 26,
    color: '#222',
  },

  subHeading: {
    textAlign: 'center',
    fontWeight: 'bold',
    marginTop: 10,
    fontSize: 18,
  },

  description: {
    textAlign: 'center',
    marginTop: 15,
    fontSize: 16,
    lineHeight: 24,
    color: '#444',
    paddingHorizontal: 20,
  },

  courseButton: {
    backgroundColor: '#8cb6a2',
    marginTop: 20,
    padding: 16,
    borderRadius: 12,
    alignItems: 'center',
  },

  courseButtonText: {
    fontWeight: 'bold',
    fontSize: 16,
  },

  screenContainer: {
    flex: 1,
    backgroundColor: '#f5f5f5',
    padding: 16,
  },

  headerBar: {
    flexDirection: 'row',
    alignItems: 'center',
    marginTop: 10,
    marginBottom: 20,
  },

  dropdownBox: {
    flexDirection: 'row',
    backgroundColor: '#8cb6a2',
    padding: 10,
    borderRadius: 10,
    alignItems: 'center',
    marginLeft: 20,
    flex: 1,
    justifyContent: 'space-between',
  },

  dropdownText: {
    fontWeight: 'bold',
  },

  courseCard: {
    flexDirection: 'row',
    backgroundColor: '#fff',
    padding: 12,
    borderRadius: 10,
    marginBottom: 15,
    alignItems: 'center',
  },

  courseImage: {
    width: 70,
    height: 70,
    marginRight: 10,
  },

  courseInfo: {
    flex: 1,
  },

  courseTitle: {
    fontWeight: 'bold',
    fontSize: 16,
  },

  coursePrice: {
    color: '#555',
    marginBottom: 5,
  },

  courseDescription: {
    color: '#666',
    fontSize: 13,
  },

  bottomButtons: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    marginTop: 20,
    marginBottom: 40,
  },

  backButton: {
    backgroundColor: '#f2c94c',
    paddingVertical: 10,
    paddingHorizontal: 25,
    borderRadius: 20,
  },

  nextButton: {
    backgroundColor: '#0f5f1f',
    paddingVertical: 10,
    paddingHorizontal: 25,
    borderRadius: 20,
  },

  buttonText: {
    color: '#fff',
    fontWeight: 'bold',
  },

  calculateHeading: {
    backgroundColor: '#8cb6a2',
    alignSelf: 'center',
    padding: 12,
    borderRadius: 10,
    fontWeight: 'bold',
    marginBottom: 20,
    marginTop: 20,
  },

  formLabel: {
    marginTop: 10,
    fontWeight: 'bold',
  },

  formInput: {
    backgroundColor: '#fff',
    borderRadius: 12,
    padding: 14,
    marginTop: 8,
  },

  selectText: {
    marginTop: 20,
    fontWeight: 'bold',
    marginBottom: 10,
  },

  checkboxRow: {
    flexDirection: 'row',
    alignItems: 'center',
    marginBottom: 15,
  },

  checkbox: {
    width: 22,
    height: 22,
    borderWidth: 2,
    borderColor: '#58a58c',
    marginRight: 10,
    borderRadius: 5,
  },

  calculateButton: {
    backgroundColor: '#8cb6a2',
    padding: 16,
    borderRadius: 12,
    alignItems: 'center',
    marginTop: 20,
  },

  calculateButtonText: {
    fontWeight: 'bold',
    color: '#fff',
  },

  summaryHeading: {
    alignSelf: 'center',
    backgroundColor: '#8cb6a2',
    padding: 12,
    borderRadius: 10,
    marginTop: 20,
    fontWeight: 'bold',
  },

  summaryBox: {
    backgroundColor: '#fff',
    padding: 20,
    borderRadius: 10,
    marginTop: 20,
  },

  line: {
    height: 1,
    backgroundColor: '#999',
    marginVertical: 10,
  },

  totalQuoteButton: {
    backgroundColor: '#8cb6a2',
    padding: 16,
    borderRadius: 12,
    alignItems: 'center',
    marginTop: 20,
  },

  totalQuoteText: {
    color: '#fff',
    fontWeight: 'bold',
  },

  consultButton: {
    backgroundColor: '#8cb6a2',
    padding: 16,
    borderRadius: 12,
    alignItems: 'center',
    marginTop: 30,
  },

  consultButtonText: {
    color: '#fff',
    fontWeight: 'bold',
  },

  contactHeading: {
    alignSelf: 'center',
    backgroundColor: '#8cb6a2',
    padding: 12,
    borderRadius: 10,
    marginTop: 20,
    fontWeight: 'bold',
  },

  campusDropdown: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    alignItems: 'center',
    backgroundColor: '#fff',
    padding: 16,
    borderRadius: 12,
    marginTop: 20,
  },

  contactCard: {
    flexDirection: 'row',
    alignItems: 'center',
    marginTop: 25,
  },

  contactText: {
    marginLeft: 15,
    fontSize: 16,
    color: '#333',
  },

  mapButton: {
    backgroundColor: '#8cb6a2',
    padding: 14,
    borderRadius: 10,
    alignItems: 'center',
    marginTop: 20,
  },

  mapButtonText: {
    color: '#fff',
    fontWeight: 'bold',
  },
});
